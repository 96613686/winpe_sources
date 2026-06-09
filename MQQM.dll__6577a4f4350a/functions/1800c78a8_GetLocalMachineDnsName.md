# GetLocalMachineDnsName

- ea: `0x1800c78a8`
- end: `0x1800c797b`
- name: `GetLocalMachineDnsName`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800c7984`

## callees

- `0x18000f35c`
- `0x18009bd1c`
- `0x1800c78a8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800c78cd`
- `KERNEL32!GetLastError` at `0x1800c7935`
- `KERNEL32!GetLastError` at `0x1800c78cd`
- `KERNEL32!GetLastError` at `0x1800c7935`
- `KERNEL32!GetComputerNameExW` at `0x1800c78c3`
- `KERNEL32!GetComputerNameExW` at `0x1800c792b`
- `KERNEL32!GetComputerNameExW` at `0x1800c78c3`
- `KERNEL32!GetComputerNameExW` at `0x1800c792b`

## pseudocode

```c
__int64 __fastcall GetLocalMachineDnsName(WCHAR **a1)
{
  DWORD LastError; // eax
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  WCHAR *v5; // rax
  DWORD nSize; // [rsp+38h] [rbp+10h] BYREF

  nSize = 0;
  if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, 0, &nSize) )
  {
    LastError = GetLastError();
    if ( LastError != 234 )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return 0;
      v4 = 13;
LABEL_10:
      WPP_SF_d(v3[2], v4, WPP_e54437e9c8b438399f706fc9b765c57c_Traceguids, LastError);
      return 0;
    }
  }
  v5 = (WCHAR *)MmAllocate(saturated_mul(nSize + 1, 2u));
  *a1 = v5;
  if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, v5, &nSize) )
  {
    LastError = GetLastError();
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v4 = 14;
    goto LABEL_10;
  }
  return 1;
}

```

## disassembly

```asm
0x1800c78a8  push    rbx
0x1800c78aa  sub     rsp, 20h
0x1800c78ae  xor     edx, edx; lpBuffer
0x1800c78b0  mov     [rsp+28h+nSize], 0
0x1800c78b8  mov     rbx, rcx
0x1800c78bb  lea     r8, [rsp+28h+nSize]; nSize
0x1800c78c0  lea     ecx, [rdx+3]; NameType
0x1800c78c3  call    cs:__imp_GetComputerNameExW
0x1800c78c9  test    eax, eax
0x1800c78cb  jnz     short loc_1800C78FA
0x1800c78cd  call    cs:__imp_GetLastError
0x1800c78d3  cmp     eax, 0EAh
0x1800c78d8  jz      short loc_1800C78FA
0x1800c78da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c78e1  lea     rdx, WPP_GLOBAL_Control
0x1800c78e8  cmp     rcx, rdx
0x1800c78eb  jz      short loc_1800C796C
0x1800c78ed  test    byte ptr [rcx+1Ch], 1
0x1800c78f1  jz      short loc_1800C796C
0x1800c78f3  mov     edx, 0Dh
0x1800c78f8  jmp     short loc_1800C7959
0x1800c78fa  mov     edx, [rsp+28h+nSize]
0x1800c78fe  mov     eax, 2
0x1800c7903  inc     edx
0x1800c7905  mul     rdx
0x1800c7908  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1800c790f  cmovb   rax, rdx
0x1800c7913  mov     rcx, rax; unsigned __int64
0x1800c7916  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800c791b  lea     r8, [rsp+28h+nSize]; nSize
0x1800c7920  mov     [rbx], rax
0x1800c7923  mov     rdx, rax; lpBuffer
0x1800c7926  mov     ecx, 3; NameType
0x1800c792b  call    cs:__imp_GetComputerNameExW
0x1800c7931  test    eax, eax
0x1800c7933  jnz     short loc_1800C7970
0x1800c7935  call    cs:__imp_GetLastError
0x1800c793b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7942  lea     rdx, WPP_GLOBAL_Control
0x1800c7949  cmp     rcx, rdx
0x1800c794c  jz      short loc_1800C796C
0x1800c794e  test    byte ptr [rcx+1Ch], 1
0x1800c7952  jz      short loc_1800C796C
0x1800c7954  mov     edx, 0Eh
0x1800c7959  mov     rcx, [rcx+10h]
0x1800c795d  lea     r8, WPP_e54437e9c8b438399f706fc9b765c57c_Traceguids
0x1800c7964  mov     r9d, eax
0x1800c7967  call    WPP_SF_d
0x1800c796c  xor     eax, eax
0x1800c796e  jmp     short loc_1800C7975
0x1800c7970  mov     eax, 1
0x1800c7975  add     rsp, 20h
0x1800c7979  pop     rbx
0x1800c797a  retn
```
