# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x140008864`
- end: `0x140008933`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140005ff0`

## callees

- `0x140007370`
- `0x1400083f0`
- `0x140008864`

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
0x140008864  push    rbx
0x140008866  push    rbp
0x140008867  push    rsi
0x140008868  push    rdi
0x140008869  sub     rsp, 28h
0x14000886d  cmp     qword ptr [rcx+18h], 0
0x140008872  mov     rsi, rdx
0x140008875  mov     edi, [rcx+10h]
0x140008878  mov     rbx, rcx
0x14000887b  mov     ebp, 50h ; 'P'
0x140008880  jnz     short loc_1400088B7
0x140008882  test    edi, edi
0x140008884  jz      short loc_1400088B7
0x140008886  mov     edx, 190h; dwBytes
0x14000888b  lea     ecx, [rbp-48h]; dwFlags
0x14000888e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140008893  mov     [rbx+18h], rax
0x140008897  test    rax, rax
0x14000889a  jz      short loc_1400088B7
0x14000889c  mov     dword ptr [rbx+20h], 5
0x1400088a3  lea     rcx, [rax+190h]
0x1400088aa  jmp     short loc_1400088B2
0x1400088ac  mov     [rax], bp
0x1400088af  add     rax, rbp
0x1400088b2  cmp     rax, rcx
0x1400088b5  jnz     short loc_1400088AC
0x1400088b7  mov     r9, [rbx+18h]
0x1400088bb  test    r9, r9
0x1400088be  jz      short loc_14000892A
0x1400088c0  test    edi, edi
0x1400088c2  jz      short loc_1400088F0
0x1400088c4  movzx   eax, word ptr [rbx+20h]
0x1400088c8  mov     rcx, r9
0x1400088cb  lea     rdx, [rax+rax*4]
0x1400088cf  shl     rdx, 4
0x1400088d3  add     rdx, r9
0x1400088d6  cmp     rcx, rdx
0x1400088d9  jz      short loc_1400088F0
0x1400088db  mov     eax, [rbx+10h]
0x1400088de  cmp     [rcx+4], eax
0x1400088e1  jbe     short loc_1400088EB
0x1400088e3  mov     eax, [rsi+8]
0x1400088e6  cmp     [rcx+8], eax
0x1400088e9  jz      short loc_14000892A
0x1400088eb  add     rcx, rbp
0x1400088ee  jmp     short loc_1400088D6
0x1400088f0  movzx   eax, word ptr [rbx+22h]
0x1400088f4  xor     edx, edx
0x1400088f6  movzx   ecx, word ptr [rbx+20h]
0x1400088fa  inc     eax
0x1400088fc  div     ecx
0x1400088fe  mov     rax, [rbx+8]
0x140008902  mov     r8d, 1
0x140008908  mov     [rbx+22h], dx
0x14000890c  lock xadd [rax], r8d
0x140008911  movzx   eax, dx
0x140008914  inc     r8d; unsigned int
0x140008917  mov     rdx, rsi; struct wil::FailureInfo *
0x14000891a  lea     rcx, [rax+rax*4]
0x14000891e  shl     rcx, 4
0x140008922  add     rcx, r9; this
0x140008925  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000892a  add     rsp, 28h
0x14000892e  pop     rdi
0x14000892f  pop     rsi
0x140008930  pop     rbp
0x140008931  pop     rbx
0x140008932  retn
```
