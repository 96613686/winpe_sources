# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x40b2ec`
- end: `0x40b3a1`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QAEXABUFailureInfo@3@@Z`
- size: `181`
- prototype: `void __thiscall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x40b5e0`

## callees

- `0x40a6b9`
- `0x40b164`
- `0x40b2ec`

## pseudocode

```c
void __thiscall wil::details_abi::ThreadLocalData::SetLastError(
        wil::details_abi::ThreadLocalData *this,
        const struct wil::FailureInfo *a2)
{
  int v3; // ebx
  _WORD *v4; // eax
  _WORD *v5; // ecx
  int v6; // edi
  int v7; // ecx
  int v8; // edx
  unsigned int v9; // eax
  unsigned int v10; // eax

  v3 = *((_DWORD *)this + 3);
  if ( !*((_DWORD *)this + 4) )
  {
    if ( v3 )
    {
      v4 = wil::details::ProcessHeapAlloc(8u, 0xDCu);
      *((_DWORD *)this + 4) = v4;
      if ( v4 )
      {
        *((_WORD *)this + 10) = 5;
        *((_WORD *)this + 11) = 0;
        v5 = v4 + 110;
        while ( v4 != v5 )
        {
          *v4 = 44;
          v4 += 22;
        }
      }
    }
  }
  v6 = *((_DWORD *)this + 4);
  if ( v6 )
  {
    if ( v3 )
    {
      v7 = *((_DWORD *)this + 4);
      v8 = v6 + 44 * *((unsigned __int16 *)this + 10);
      if ( v6 != v8 )
      {
        v9 = *((_DWORD *)this + 3);
        do
        {
          if ( *(_DWORD *)(v7 + 4) > v9 )
          {
            if ( *(_DWORD *)(v7 + 8) == *((_DWORD *)a2 + 2) )
              return;
            v9 = *((_DWORD *)this + 3);
          }
          v7 += 44;
        }
        while ( v7 != v8 );
      }
    }
    v10 = ((unsigned int)*((unsigned __int16 *)this + 11) + 1) % *((unsigned __int16 *)this + 10);
    *((_WORD *)this + 11) = v10;
    wil::details_abi::ThreadLocalFailureInfo::Set(
      (wil::details_abi::ThreadLocalFailureInfo *)(v6 + 44 * v10),
      a2,
      _InterlockedIncrement(*((volatile signed __int32 **)this + 2)));
  }
}

```

## disassembly

```asm
0x40b2ec  mov     edi, edi
0x40b2ee  push    ebp
0x40b2ef  mov     ebp, esp
0x40b2f1  push    ebx; unsigned int
0x40b2f2  push    esi; unsigned int
0x40b2f3  mov     esi, ecx
0x40b2f5  push    edi; this
0x40b2f6  push    2Ch ; ','
0x40b2f8  pop     edi
0x40b2f9  cmp     dword ptr [esi+10h], 0
0x40b2fd  mov     ebx, [esi+0Ch]
0x40b300  jnz     short loc_40B338
0x40b302  test    ebx, ebx
0x40b304  jz      short loc_40B338
0x40b306  push    8
0x40b308  mov     edx, 0DCh
0x40b30d  pop     ecx
0x40b30e  call    ?ProcessHeapAlloc@details@wil@@YGPAXKI@Z; wil::details::ProcessHeapAlloc(ulong,uint)
0x40b313  mov     [esi+10h], eax
0x40b316  test    eax, eax
0x40b318  jz      short loc_40B338
0x40b31a  push    5
0x40b31c  pop     ecx
0x40b31d  mov     [esi+14h], cx
0x40b321  xor     ecx, ecx
0x40b323  mov     [esi+16h], cx
0x40b327  lea     ecx, [eax+0DCh]
0x40b32d  jmp     short loc_40B334
0x40b32f  mov     [eax], di
0x40b332  add     eax, edi
0x40b334  cmp     eax, ecx
0x40b336  jnz     short loc_40B32F
0x40b338  mov     edi, [esi+10h]
0x40b33b  test    edi, edi
0x40b33d  jz      short loc_40B39A
0x40b33f  test    ebx, ebx
0x40b341  mov     ebx, [ebp+arg_0]
0x40b344  jz      short loc_40B36F
0x40b346  movzx   eax, word ptr [esi+14h]
0x40b34a  mov     ecx, edi
0x40b34c  imul    edx, eax, 2Ch ; ','
0x40b34f  add     edx, edi
0x40b351  cmp     edi, edx
0x40b353  jz      short loc_40B36F
0x40b355  mov     eax, [esi+0Ch]
0x40b358  cmp     [ecx+4], eax
0x40b35b  jbe     short loc_40B368
0x40b35d  mov     eax, [ecx+8]
0x40b360  cmp     eax, [ebx+8]
0x40b363  jz      short loc_40B39A
0x40b365  mov     eax, [esi+0Ch]
0x40b368  add     ecx, 2Ch ; ','
0x40b36b  cmp     ecx, edx
0x40b36d  jnz     short loc_40B358
0x40b36f  movzx   eax, word ptr [esi+16h]
0x40b373  xor     edx, edx
0x40b375  movzx   ecx, word ptr [esi+14h]
0x40b379  inc     eax
0x40b37a  div     ecx
0x40b37c  movzx   eax, dx
0x40b37f  xor     edx, edx
0x40b381  imul    ecx, eax, 2Ch ; ','
0x40b384  inc     edx
0x40b385  mov     [esi+16h], ax
0x40b389  mov     eax, [esi+8]
0x40b38c  add     ecx, edi; this
0x40b38e  lock xadd [eax], edx
0x40b392  inc     edx
0x40b393  push    edx; unsigned int
0x40b394  push    ebx; struct wil::FailureInfo *
0x40b395  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QAEXABUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x40b39a  pop     edi
0x40b39b  pop     esi
0x40b39c  pop     ebx
0x40b39d  pop     ebp
0x40b39e  retn    4
```
