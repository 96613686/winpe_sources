# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x140005174`
- end: `0x140005243`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400038f0`

## callees

- `0x140004958`
- `0x140004ddc`
- `0x140005174`

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
0x140005174  push    rbx
0x140005176  push    rbp
0x140005177  push    rsi
0x140005178  push    rdi
0x140005179  sub     rsp, 28h
0x14000517d  cmp     qword ptr [rcx+18h], 0
0x140005182  mov     rsi, rdx
0x140005185  mov     edi, [rcx+10h]
0x140005188  mov     rbx, rcx
0x14000518b  mov     ebp, 50h ; 'P'
0x140005190  jnz     short loc_1400051C7
0x140005192  test    edi, edi
0x140005194  jz      short loc_1400051C7
0x140005196  mov     edx, 190h; dwBytes
0x14000519b  lea     ecx, [rbp-48h]; dwFlags
0x14000519e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400051a3  mov     [rbx+18h], rax
0x1400051a7  test    rax, rax
0x1400051aa  jz      short loc_1400051C7
0x1400051ac  mov     dword ptr [rbx+20h], 5
0x1400051b3  lea     rcx, [rax+190h]
0x1400051ba  jmp     short loc_1400051C2
0x1400051bc  mov     [rax], bp
0x1400051bf  add     rax, rbp
0x1400051c2  cmp     rax, rcx
0x1400051c5  jnz     short loc_1400051BC
0x1400051c7  mov     r9, [rbx+18h]
0x1400051cb  test    r9, r9
0x1400051ce  jz      short loc_14000523A
0x1400051d0  test    edi, edi
0x1400051d2  jz      short loc_140005200
0x1400051d4  movzx   eax, word ptr [rbx+20h]
0x1400051d8  mov     rcx, r9
0x1400051db  lea     rdx, [rax+rax*4]
0x1400051df  shl     rdx, 4
0x1400051e3  add     rdx, r9
0x1400051e6  cmp     rcx, rdx
0x1400051e9  jz      short loc_140005200
0x1400051eb  mov     eax, [rbx+10h]
0x1400051ee  cmp     [rcx+4], eax
0x1400051f1  jbe     short loc_1400051FB
0x1400051f3  mov     eax, [rsi+8]
0x1400051f6  cmp     [rcx+8], eax
0x1400051f9  jz      short loc_14000523A
0x1400051fb  add     rcx, rbp
0x1400051fe  jmp     short loc_1400051E6
0x140005200  movzx   eax, word ptr [rbx+22h]
0x140005204  xor     edx, edx
0x140005206  movzx   ecx, word ptr [rbx+20h]
0x14000520a  inc     eax
0x14000520c  div     ecx
0x14000520e  mov     rax, [rbx+8]
0x140005212  mov     r8d, 1
0x140005218  mov     [rbx+22h], dx
0x14000521c  lock xadd [rax], r8d
0x140005221  movzx   eax, dx
0x140005224  inc     r8d; unsigned int
0x140005227  mov     rdx, rsi; struct wil::FailureInfo *
0x14000522a  lea     rcx, [rax+rax*4]
0x14000522e  shl     rcx, 4
0x140005232  add     rcx, r9; this
0x140005235  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000523a  add     rsp, 28h
0x14000523e  pop     rdi
0x14000523f  pop     rsi
0x140005240  pop     rbp
0x140005241  pop     rbx
0x140005242  retn
```
