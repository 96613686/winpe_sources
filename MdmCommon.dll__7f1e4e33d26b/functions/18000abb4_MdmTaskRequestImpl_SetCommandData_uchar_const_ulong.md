# MdmTaskRequestImpl::SetCommandData(uchar const *,ulong)

- ea: `0x18000abb4`
- end: `0x18000ac75`
- name: `?SetCommandData@MdmTaskRequestImpl@@QEAAJPEBEK@Z`
- size: `193`
- prototype: `__int64 __fastcall(MdmTaskRequestImpl *this, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000745c`

## callees

- `0x180001544`
- `0x1800015b8`
- `0x180006548`
- `0x18000abb4`
- `0x18001d510`

## string_xrefs

- `0x18000ac29`: `CPR(pbCommandDataCopy)`
- `0x18000abdf`: `CBR(pbCommandData)`
- `0x18000abf3`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmtaskrequestimpl.cpp`

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
          (__int64)"CPR(pbCommandDataCopy)");
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
        (__int64)"CBR(pbCommandData)");
  }
  return v6;
}

```

## disassembly

```asm
0x18000abb4  push    rbx
0x18000abb6  push    rbp
0x18000abb7  push    rsi
0x18000abb8  push    rdi
0x18000abb9  push    r14
0x18000abbb  sub     rsp, 30h
0x18000abbf  mov     ebp, r8d
0x18000abc2  mov     r14, rdx
0x18000abc5  mov     rdi, rcx
0x18000abc8  test    rdx, rdx
0x18000abcb  jnz     short loc_18000AC04
0x18000abcd  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000abd4  mov     ebx, 80004003h
0x18000abd9  jz      loc_18000AC68
0x18000abdf  lea     rax, aCbrPbcommandda; "CBR(pbCommandData)"
0x18000abe6  mov     [rsp+58h+var_30], rax
0x18000abeb  mov     [rsp+58h+var_38], 38h ; '8'
0x18000abf3  lea     r9, aOnecoreuapShel_1; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000abfa  mov     r8d, ebx
0x18000abfd  call    McTemplateU0dsqs_EventWriteTransfer
0x18000ac02  jmp     short loc_18000AC68
0x18000ac04  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ac0b  mov     rcx, rbp; unsigned __int64
0x18000ac0e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000ac13  mov     rsi, rax
0x18000ac16  test    rax, rax
0x18000ac19  jnz     short loc_18000AC3F
0x18000ac1b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000ac22  mov     ebx, 8007000Eh
0x18000ac27  jz      short loc_18000AC68
0x18000ac29  lea     rax, aCprPbcommandda; "CPR(pbCommandDataCopy)"
0x18000ac30  mov     [rsp+58h+var_30], rax
0x18000ac35  mov     [rsp+58h+var_38], 3Ch ; '<'
0x18000ac3d  jmp     short loc_18000ABF3
0x18000ac3f  test    ebp, ebp
0x18000ac41  jz      short loc_18000AC51
0x18000ac43  mov     r8, rbp; Size
0x18000ac46  mov     rdx, r14; Src
0x18000ac49  mov     rcx, rsi; void *
0x18000ac4c  call    memcpy_0
0x18000ac51  mov     rcx, [rdi+10h]; void *
0x18000ac55  xor     ebx, ebx
0x18000ac57  test    rcx, rcx
0x18000ac5a  jz      short loc_18000AC61
0x18000ac5c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ac61  mov     [rdi+10h], rsi
0x18000ac65  mov     [rdi+18h], ebp
0x18000ac68  mov     eax, ebx
0x18000ac6a  add     rsp, 30h
0x18000ac6e  pop     r14
0x18000ac70  pop     rdi
0x18000ac71  pop     rsi
0x18000ac72  pop     rbp
0x18000ac73  pop     rbx
0x18000ac74  retn
```
