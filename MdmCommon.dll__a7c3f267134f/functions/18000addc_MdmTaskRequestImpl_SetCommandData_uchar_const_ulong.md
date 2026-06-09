# MdmTaskRequestImpl::SetCommandData(uchar const *,ulong)

- ea: `0x18000addc`
- end: `0x18000ae9e`
- name: `?SetCommandData@MdmTaskRequestImpl@@QEAAJPEBEK@Z`
- size: `194`
- prototype: `__int64 __fastcall(MdmTaskRequestImpl *this, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800074e4`

## callees

- `0x180001544`
- `0x1800015b8`
- `0x1800065c0`
- `0x18000addc`
- `0x18001dbf0`

## string_xrefs

- `0x18000ae51`: `CPR(pbCommandDataCopy)`
- `0x18000ae07`: `CBR(pbCommandData)`
- `0x18000ae1b`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmtaskrequestimpl.cpp`

## pseudocode

```c
__int64 __fastcall MdmTaskRequestImpl::SetCommandData(
        MdmTaskRequestImpl *this,
        const unsigned __int8 *a2,
        unsigned int a3)
{
  size_t v3; // rbp
  unsigned int v6; // ebx
  void *v7; // rax
  unsigned __int64 v8; // rdx
  int v9; // ecx
  void *v10; // rsi
  void *v11; // rcx

  v3 = a3;
  if ( a2 )
  {
    v7 = operator new[](a3, (const struct std::nothrow_t *)&std::nothrow);
    v10 = v7;
    if ( v7 )
    {
      if ( (_DWORD)v3 )
        memcpy_0(v7, a2, v3);
      v11 = (void *)*((_QWORD *)this + 2);
      v6 = 0;
      if ( v11 )
        operator delete(v11, v8);
      *((_QWORD *)this + 2) = v10;
      *((_DWORD *)this + 6) = v3;
    }
    else
    {
      v6 = -2147024882;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v9,
          v8,
          -2147024882,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestimpl.cpp",
          60,
          "CPR(pbCommandDataCopy)");
    }
  }
  else
  {
    v6 = -2147467261;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)this,
        0,
        -2147467261,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestimpl.cpp",
        56,
        "CBR(pbCommandData)");
  }
  return v6;
}

```

## disassembly

```asm
0x18000addc  push    rbx
0x18000adde  push    rbp
0x18000addf  push    rsi
0x18000ade0  push    rdi
0x18000ade1  push    r14
0x18000ade3  sub     rsp, 30h
0x18000ade7  mov     ebp, r8d
0x18000adea  mov     r14, rdx
0x18000aded  mov     rdi, rcx
0x18000adf0  test    rdx, rdx
0x18000adf3  jnz     short loc_18000AE2C
0x18000adf5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000adfc  mov     ebx, 80004003h
0x18000ae01  jz      loc_18000AE90
0x18000ae07  lea     rax, aCbrPbcommandda; "CBR(pbCommandData)"
0x18000ae0e  mov     [rsp+58h+var_30], rax
0x18000ae13  mov     [rsp+58h+var_38], 38h ; '8'
0x18000ae1b  lea     r9, aOnecoreuapShel_1; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000ae22  mov     r8d, ebx
0x18000ae25  call    McTemplateU0dsqs_EventWriteTransfer
0x18000ae2a  jmp     short loc_18000AE90
0x18000ae2c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ae33  mov     rcx, rbp; unsigned __int64
0x18000ae36  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000ae3b  mov     rsi, rax
0x18000ae3e  test    rax, rax
0x18000ae41  jnz     short loc_18000AE67
0x18000ae43  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000ae4a  mov     ebx, 8007000Eh
0x18000ae4f  jz      short loc_18000AE90
0x18000ae51  lea     rax, aCprPbcommandda; "CPR(pbCommandDataCopy)"
0x18000ae58  mov     [rsp+58h+var_30], rax
0x18000ae5d  mov     [rsp+58h+var_38], 3Ch ; '<'
0x18000ae65  jmp     short loc_18000AE1B
0x18000ae67  test    ebp, ebp
0x18000ae69  jz      short loc_18000AE79
0x18000ae6b  mov     r8, rbp; Size
0x18000ae6e  mov     rdx, r14; Src
0x18000ae71  mov     rcx, rsi; void *
0x18000ae74  call    memcpy_0
0x18000ae79  mov     rcx, [rdi+10h]; void *
0x18000ae7d  xor     ebx, ebx
0x18000ae7f  test    rcx, rcx
0x18000ae82  jz      short loc_18000AE89
0x18000ae84  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ae89  mov     [rdi+10h], rsi
0x18000ae8d  mov     [rdi+18h], ebp
0x18000ae90  mov     eax, ebx
0x18000ae92  add     rsp, 30h
0x18000ae96  pop     r14
0x18000ae98  pop     rdi
0x18000ae99  pop     rsi
0x18000ae9a  pop     rbp
0x18000ae9b  pop     rbx
0x18000ae9c  retn
```
