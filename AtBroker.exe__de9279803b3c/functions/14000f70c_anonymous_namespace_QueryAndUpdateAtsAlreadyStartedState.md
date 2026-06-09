# _anonymous_namespace_::QueryAndUpdateAtsAlreadyStartedState

- ea: `0x14000f70c`
- end: `0x14000f80a`
- name: `_anonymous_namespace_::QueryAndUpdateAtsAlreadyStartedState`
- size: `254`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140010714`

## callees

- `0x14000ab98`
- `0x14000f70c`

## import_xrefs

- `ntdll!NtUpdateWnfStateData` at `0x14000f7c9`
- `ntdll!NtUpdateWnfStateData` at `0x14000f7c9`
- `ntdll!NtQueryWnfStateData` at `0x14000f74d`
- `ntdll!NtQueryWnfStateData` at `0x14000f74d`

## pseudocode

```c
__int64 anonymous_namespace_::QueryAndUpdateAtsAlreadyStartedState()
{
  int v0; // eax
  int v1; // eax
  unsigned int v3; // [rsp+60h] [rbp+18h] BYREF
  int v4; // [rsp+68h] [rbp+20h] BYREF
  int v5; // [rsp+70h] [rbp+28h] BYREF
  int v6; // [rsp+78h] [rbp+30h] BYREF

  v5 = 0;
  v4 = 4;
  v3 = 0;
  v0 = NtQueryWnfStateData(&WNF_EOA_ATMANAGER_ATS_STARTED, 0, 0, &v5, &v3, &v4) | 0x10000000;
  if ( v0 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids,
      (unsigned int)v0);
  if ( !v3 )
  {
    v6 = 1;
    v4 = 4;
    v1 = NtUpdateWnfStateData(&WNF_EOA_ATMANAGER_ATS_STARTED, &v6, 4) | 0x10000000;
    if ( v1 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids,
        (unsigned int)v1);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14000f70c  push    rbp
0x14000f70e  push    rdi
0x14000f70f  mov     rbp, rsp
0x14000f712  sub     rsp, 48h
0x14000f716  lea     rax, [rbp+arg_8]
0x14000f71a  mov     [rbp+arg_10], 0
0x14000f721  mov     [rsp+48h+var_20], rax
0x14000f726  lea     r9, [rbp+arg_10]
0x14000f72a  lea     rax, [rbp+arg_0]
0x14000f72e  mov     [rbp+arg_8], 4
0x14000f735  xor     r8d, r8d
0x14000f738  mov     [rsp+48h+var_28], rax
0x14000f73d  xor     edx, edx
0x14000f73f  mov     [rbp+arg_0], 0
0x14000f746  lea     rcx, WNF_EOA_ATMANAGER_ATS_STARTED
0x14000f74d  call    cs:__imp_NtQueryWnfStateData
0x14000f753  or      eax, 10000000h
0x14000f758  lea     rdi, WPP_GLOBAL_Control
0x14000f75f  jge     short loc_14000F78B
0x14000f761  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f768  cmp     rcx, rdi
0x14000f76b  jz      short loc_14000F78B
0x14000f76d  test    byte ptr [rcx+1Ch], 8
0x14000f771  jz      short loc_14000F78B
0x14000f773  mov     rcx, [rcx+10h]
0x14000f777  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14000f77e  mov     edx, 0Ah
0x14000f783  mov     r9d, eax
0x14000f786  call    WPP_SF_D
0x14000f78b  cmp     [rbp+arg_0], 0
0x14000f78f  jnz     short loc_14000F800
0x14000f791  mov     eax, [rbp+arg_10]
0x14000f794  lea     rdx, [rbp+arg_18]
0x14000f798  xor     r9d, r9d
0x14000f79b  mov     [rsp+48h+var_18], 0
0x14000f7a3  mov     dword ptr [rsp+48h+var_20], eax
0x14000f7a7  lea     rcx, WNF_EOA_ATMANAGER_ATS_STARTED
0x14000f7ae  mov     [rbp+arg_18], 1
0x14000f7b5  mov     [rbp+arg_8], 4
0x14000f7bc  lea     r8d, [r9+4]
0x14000f7c0  mov     [rsp+48h+var_28], 0
0x14000f7c9  call    cs:__imp_NtUpdateWnfStateData
0x14000f7cf  or      eax, 10000000h
0x14000f7d4  jge     short loc_14000F800
0x14000f7d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f7dd  cmp     rcx, rdi
0x14000f7e0  jz      short loc_14000F800
0x14000f7e2  test    byte ptr [rcx+1Ch], 8
0x14000f7e6  jz      short loc_14000F800
0x14000f7e8  mov     rcx, [rcx+10h]
0x14000f7ec  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14000f7f3  mov     edx, 0Bh
0x14000f7f8  mov     r9d, eax
0x14000f7fb  call    WPP_SF_D
0x14000f800  mov     eax, [rbp+arg_0]
0x14000f803  add     rsp, 48h
0x14000f807  pop     rdi
0x14000f808  pop     rbp
0x14000f809  retn
```
