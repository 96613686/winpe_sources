# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180005850`
- end: `0x180005920`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `208`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800037b0`

## callees

- `0x180004f80`
- `0x18000549c`
- `0x180005850`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::SetLastError(
        wil::details_abi::ThreadLocalData *this,
        const struct wil::FailureInfo *a2)
{
  int v3; // edi
  _WORD *v5; // rax
  _WORD *v6; // rcx
  __int64 v7; // r9
  __int64 i; // rcx
  unsigned __int16 v9; // dx
  volatile signed __int32 *v10; // rax

  v3 = *((_DWORD *)this + 4);
  if ( !*((_QWORD *)this + 3) )
  {
    if ( v3 )
    {
      v5 = wil::details::ProcessHeapAlloc(8u, 0x190u);
      *((_QWORD *)this + 3) = v5;
      if ( v5 )
      {
        *((_DWORD *)this + 8) = 5;
        v6 = v5 + 200;
        while ( v5 != v6 )
        {
          *v5 = 80;
          v5 += 40;
        }
      }
    }
  }
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
  {
    if ( v3 )
    {
      for ( i = *((_QWORD *)this + 3); i != v7 + 80LL * *((unsigned __int16 *)this + 16); i += 80 )
      {
        if ( *(_DWORD *)(i + 4) > *((_DWORD *)this + 4) && *(_DWORD *)(i + 8) == *((_DWORD *)a2 + 2) )
          return;
      }
    }
    v9 = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
    v10 = (volatile signed __int32 *)*((_QWORD *)this + 1);
    *((_WORD *)this + 17) = v9;
    wil::details_abi::ThreadLocalFailureInfo::Set(
      (wil::details_abi::ThreadLocalFailureInfo *)(v7 + 80LL * v9),
      a2,
      _InterlockedIncrement(v10));
  }
}

```

## disassembly

```asm
0x180005850  push    rbx
0x180005852  push    rbp
0x180005853  push    rsi
0x180005854  push    rdi
0x180005855  sub     rsp, 28h
0x180005859  cmp     qword ptr [rcx+18h], 0
0x18000585e  mov     rsi, rdx
0x180005861  mov     edi, [rcx+10h]
0x180005864  mov     rbx, rcx
0x180005867  mov     ebp, 50h ; 'P'
0x18000586c  jnz     short loc_1800058A3
0x18000586e  test    edi, edi
0x180005870  jz      short loc_1800058A3
0x180005872  mov     edx, 190h; dwBytes
0x180005877  lea     ecx, [rbp-48h]; dwFlags
0x18000587a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000587f  mov     [rbx+18h], rax
0x180005883  test    rax, rax
0x180005886  jz      short loc_1800058A3
0x180005888  mov     dword ptr [rbx+20h], 5
0x18000588f  lea     rcx, [rax+190h]
0x180005896  jmp     short loc_18000589E
0x180005898  mov     [rax], bp
0x18000589b  add     rax, rbp
0x18000589e  cmp     rax, rcx
0x1800058a1  jnz     short loc_180005898
0x1800058a3  mov     r9, [rbx+18h]
0x1800058a7  test    r9, r9
0x1800058aa  jz      short loc_180005916
0x1800058ac  test    edi, edi
0x1800058ae  jz      short loc_1800058DC
0x1800058b0  movzx   eax, word ptr [rbx+20h]
0x1800058b4  mov     rcx, r9
0x1800058b7  lea     rdx, [rax+rax*4]
0x1800058bb  shl     rdx, 4
0x1800058bf  add     rdx, r9
0x1800058c2  cmp     rcx, rdx
0x1800058c5  jz      short loc_1800058DC
0x1800058c7  mov     eax, [rbx+10h]
0x1800058ca  cmp     [rcx+4], eax
0x1800058cd  jbe     short loc_1800058D7
0x1800058cf  mov     eax, [rsi+8]
0x1800058d2  cmp     [rcx+8], eax
0x1800058d5  jz      short loc_180005916
0x1800058d7  add     rcx, rbp
0x1800058da  jmp     short loc_1800058C2
0x1800058dc  movzx   eax, word ptr [rbx+22h]
0x1800058e0  xor     edx, edx
0x1800058e2  movzx   ecx, word ptr [rbx+20h]
0x1800058e6  inc     eax
0x1800058e8  div     ecx
0x1800058ea  mov     rax, [rbx+8]
0x1800058ee  mov     r8d, 1
0x1800058f4  mov     [rbx+22h], dx
0x1800058f8  lock xadd [rax], r8d
0x1800058fd  movzx   eax, dx
0x180005900  inc     r8d; unsigned int
0x180005903  mov     rdx, rsi; struct wil::FailureInfo *
0x180005906  lea     rcx, [rax+rax*4]
0x18000590a  shl     rcx, 4
0x18000590e  add     rcx, r9; this
0x180005911  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180005916  add     rsp, 28h
0x18000591a  pop     rdi
0x18000591b  pop     rsi
0x18000591c  pop     rbp
0x18000591d  pop     rbx
0x18000591e  retn
```
