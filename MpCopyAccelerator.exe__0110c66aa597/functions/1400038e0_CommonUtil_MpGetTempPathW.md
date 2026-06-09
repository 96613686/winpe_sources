# CommonUtil::MpGetTempPathW

- ea: `0x1400038e0`
- end: `0x1400039e4`
- name: `CommonUtil::MpGetTempPathW`
- size: `260`
- prototype: `__int64 __fastcall(LPWSTR lpBuffer, DWORD nBufferLength)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400038e0`
- `0x140003de4`
- `0x140004af8`
- `0x14001da4c`
- `0x14001da70`
- `0x140024c40`

## import_xrefs

- `KERNEL32!GetTempPathW` at `0x140003933`
- `KERNEL32!GetTempPathW` at `0x140003933`

## string_xrefs

- `0x14000395a`: `GetTempPath2W`
- `0x140003961`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DWORD __fastcall CommonUtil::MpGetTempPathW(LPWSTR lpBuffer, DWORD nBufferLength)
{
  int LoadedProcAddress; // eax
  bool v6[8]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v7; // [rsp+28h] [rbp-10h]

  v7 = 0;
  if ( !(unsigned int)MpIsWindowsIronOrGreater() )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_b1ecc9abb7cc30bcf0685ece08501d8e_Traceguids);
    return GetTempPathW(nBufferLength, lpBuffer);
  }
  if ( !*(_QWORD *)&qword_14003C110 )
  {
    LoadedProcAddress = CommonUtil::UtilRawGetLoadedProcAddress(
                          (CommonUtil *)v6,
                          (__int64 (**)(void))L"kernelbase.dll",
                          "GetTempPath2W",
                          0,
                          0);
    if ( LoadedProcAddress >= 0 )
    {
      _InterlockedExchange64((volatile __int64 *)&qword_14003C110, *(__int64 *)v6);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_b1ecc9abb7cc30bcf0685ece08501d8e_Traceguids,
        (unsigned int)LoadedProcAddress);
    }
  }
  if ( !*(_QWORD *)&qword_14003C110 )
    return GetTempPathW(nBufferLength, lpBuffer);
  return (*(__int64 (__fastcall **)(_QWORD, LPWSTR))&qword_14003C110)(nBufferLength, lpBuffer);
}

```

## disassembly

```asm
0x1400038e0  mov     [rsp+arg_10], rbx
0x1400038e5  push    rdi
0x1400038e6  sub     rsp, 30h
0x1400038ea  mov     edi, edx
0x1400038ec  mov     rbx, rcx
0x1400038ef  mov     [rsp+38h+var_10], 0
0x1400038f8  call    MpIsWindowsIronOrGreater
0x1400038fd  test    eax, eax
0x1400038ff  jnz     short loc_140003945
0x140003901  lea     rax, WPP_GLOBAL_Control
0x140003908  mov     rcx, cs:WPP_GLOBAL_Control
0x14000390f  cmp     rcx, rax
0x140003912  jz      short loc_14000392E
0x140003914  mov     edx, 10h
0x140003919  test    [rcx+1Ch], dl
0x14000391c  jz      short loc_14000392E
0x14000391e  lea     r8, WPP_b1ecc9abb7cc30bcf0685ece08501d8e_Traceguids
0x140003925  mov     rcx, [rcx+10h]
0x140003929  call    WPP_SF_
0x14000392e  mov     rdx, rbx; lpBuffer
0x140003931  mov     ecx, edi; nBufferLength
0x140003933  call    cs:__imp_GetTempPathW
0x140003939  nop
0x14000393a  mov     rbx, [rsp+38h+arg_10]
0x14000393f  add     rsp, 30h
0x140003943  pop     rdi
0x140003944  retn
0x140003945  mov     rax, cs:qword_14003C110
0x14000394c  nop
0x14000394d  test    rax, rax
0x140003950  jnz     short loc_1400039BA
0x140003952  mov     qword ptr [rsp+38h+var_18], rax; bool
0x140003957  xor     r9d, r9d; char *
0x14000395a  lea     r8, aGettemppath2w; "GetTempPath2W"
0x140003961  lea     rdx, aKernelbaseDll; "kernelbase.dll"
0x140003968  lea     rcx, [rsp+38h+var_18]; this
0x14000396d  call    ?UtilRawGetLoadedProcAddress@CommonUtil@@YAJPEAP6A_JXZPEB_WPEBD_N@Z; CommonUtil::UtilRawGetLoadedProcAddress(__int64 (**)(void),wchar_t const *,char const *,bool)
0x140003972  mov     r9d, eax
0x140003975  mov     ecx, eax
0x140003977  shr     ecx, 1Fh
0x14000397a  test    cl, cl
0x14000397c  jz      short loc_1400039AE
0x14000397e  lea     rax, WPP_GLOBAL_Control
0x140003985  mov     rcx, cs:WPP_GLOBAL_Control
0x14000398c  cmp     rcx, rax
0x14000398f  jz      short loc_1400039BA
0x140003991  test    byte ptr [rcx+1Ch], 1
0x140003995  jz      short loc_1400039BA
0x140003997  mov     edx, 11h
0x14000399c  lea     r8, WPP_b1ecc9abb7cc30bcf0685ece08501d8e_Traceguids
0x1400039a3  mov     rcx, [rcx+10h]
0x1400039a7  call    WPP_SF_d
0x1400039ac  jmp     short loc_1400039BA
0x1400039ae  mov     rax, qword ptr [rsp+38h+var_18]
0x1400039b3  xchg    rax, cs:qword_14003C110
0x1400039ba  mov     rax, cs:qword_14003C110
0x1400039c1  nop
0x1400039c2  test    rax, rax
0x1400039c5  jz      loc_14000392E
0x1400039cb  mov     rax, cs:qword_14003C110
0x1400039d2  nop
0x1400039d3  mov     rdx, rbx
0x1400039d6  mov     ecx, edi
0x1400039d8  call    cs:__guard_dispatch_icall_fptr
0x1400039de  jmp     loc_14000393A
```
