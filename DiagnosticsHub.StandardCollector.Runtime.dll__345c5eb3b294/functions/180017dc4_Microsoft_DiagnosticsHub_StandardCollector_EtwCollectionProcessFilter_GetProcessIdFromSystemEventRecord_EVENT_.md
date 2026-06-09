# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter::GetProcessIdFromSystemEventRecord(_EVENT_RECORD const &)

- ea: `0x180017dc4`
- end: `0x180017f1c`
- name: `?GetProcessIdFromSystemEventRecord@EtwCollectionProcessFilter@StandardCollector@DiagnosticsHub@Microsoft@@SAIAEBU_EVENT_RECORD@@@Z`
- size: `344`
- prototype: `unsigned int __fastcall(const struct _EVENT_RECORD *this)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019f70`
- `0x18001f2f0`
- `0x1800238a0`
- `0x180023a00`

## callees

- `0x180017dc4`
- `0x180041fac`
- `0x180049b50`

## import_xrefs

- `VCRUNTIME140!memcmp` at `0x180017e06`
- `VCRUNTIME140!memcmp` at `0x180017e49`
- `VCRUNTIME140!memcmp` at `0x180017e73`
- `VCRUNTIME140!memcmp` at `0x180017e9a`
- `VCRUNTIME140!memcmp` at `0x180017e06`
- `VCRUNTIME140!memcmp` at `0x180017e49`
- `VCRUNTIME140!memcmp` at `0x180017e73`
- `VCRUNTIME140!memcmp` at `0x180017e9a`

## string_xrefs

- `0x180017eb8`: `ProcessId`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter::GetProcessIdFromSystemEventRecord(
        const struct _EVENT_RECORD *this)
{
  struct _EVENT_RECORD *v2; // rdx
  __int64 v3; // r8
  struct _TDH_CONTEXT *v4; // r9
  UCHAR Opcode; // al
  unsigned int *UserData; // rax
  __int64 result; // rax
  UCHAR v8; // al
  UCHAR v9; // al
  UCHAR v10; // al
  struct _PROPERTY_DATA_DESCRIPTOR *v11; // [rsp+28h] [rbp-40h]
  unsigned int ProcessId; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v13[2]; // [rsp+48h] [rbp-20h] BYREF
  __int64 v14; // [rsp+50h] [rbp-18h]

  ProcessId = this->EventHeader.ProcessId;
  if ( !memcmp(&this->EventHeader.ProviderId, qword_180056988, 0x10u) )
  {
    Opcode = this->EventHeader.EventDescriptor.Opcode;
    if ( Opcode == 32 || Opcode == 37 || Opcode == 38 )
    {
      UserData = (unsigned int *)this->UserData;
      if ( UserData )
        return UserData[2];
      return 0;
    }
  }
  if ( ProcessId != -1 )
  {
    if ( memcmp(&this->EventHeader.ProviderId, qword_1800569B8, 0x10u)
      || (v8 = this->EventHeader.EventDescriptor.Opcode, v8 != 1) && (unsigned __int8)(v8 - 2) > 1u )
    {
      if ( memcmp(&this->EventHeader.ProviderId, qword_1800569A8, 0x10u)
        || (v9 = this->EventHeader.EventDescriptor.Opcode, v9 != 1) && (unsigned __int8)(v9 - 2) > 1u )
      {
        if ( memcmp(&this->EventHeader.ProviderId, qword_180056998, 0x10u) )
          return ProcessId;
        v10 = this->EventHeader.EventDescriptor.Opcode;
        if ( v10 != 10 && (unsigned __int8)(v10 - 2) > 1u )
          return ProcessId;
      }
    }
  }
  v14 = 0;
  *(_QWORD *)v13 = L"ProcessId";
  if ( (unsigned int)Microsoft::DiagnosticsHub::UnifiedPlatform::TdhGetProperty(
                       (Microsoft::DiagnosticsHub::UnifiedPlatform *)this,
                       v2,
                       v3,
                       v4,
                       (__int64)v13,
                       v11,
                       (__int64)&ProcessId) )
    return 0;
  result = ProcessId;
  if ( ProcessId == -1 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180017dc4  mov     [rsp+arg_8], rbx
0x180017dc9  mov     [rsp+arg_10], rsi
0x180017dce  mov     [rsp+arg_18], rdi
0x180017dd3  push    r15
0x180017dd5  sub     rsp, 60h
0x180017dd9  mov     rax, cs:__security_cookie
0x180017de0  xor     rax, rsp
0x180017de3  mov     [rsp+68h+var_10], rax
0x180017de8  mov     eax, [rcx+0Ch]
0x180017deb  lea     rdx, qword_180056988; Buf2
0x180017df2  mov     rbx, rcx
0x180017df5  mov     [rsp+68h+var_28], eax
0x180017df9  mov     r15d, 10h
0x180017dff  add     rcx, 18h; Buf1
0x180017e03  mov     r8d, r15d; Size
0x180017e06  call    cs:__imp_memcmp
0x180017e0c  test    eax, eax
0x180017e0e  jnz     short loc_180017E34
0x180017e10  mov     al, [rbx+2Dh]
0x180017e13  cmp     al, 20h ; ' '
0x180017e15  jz      short loc_180017E1F
0x180017e17  cmp     al, 25h ; '%'
0x180017e19  jz      short loc_180017E1F
0x180017e1b  cmp     al, 26h ; '&'
0x180017e1d  jnz     short loc_180017E34
0x180017e1f  mov     rax, [rbx+60h]
0x180017e23  test    rax, rax
0x180017e26  jz      loc_180017EF6
0x180017e2c  mov     eax, [rax+8]
0x180017e2f  jmp     loc_180017EF8
0x180017e34  cmp     [rsp+68h+var_28], 0FFFFFFFFh
0x180017e39  jz      short loc_180017EB8
0x180017e3b  mov     r8, r15; Size
0x180017e3e  lea     rdx, qword_1800569B8; Buf2
0x180017e45  lea     rcx, [rbx+18h]; Buf1
0x180017e49  call    cs:__imp_memcmp
0x180017e4f  mov     sil, 1
0x180017e52  test    eax, eax
0x180017e54  jnz     short loc_180017E65
0x180017e56  mov     al, [rbx+2Dh]
0x180017e59  cmp     al, sil
0x180017e5c  jz      short loc_180017EB8
0x180017e5e  sub     al, 2
0x180017e60  cmp     al, sil
0x180017e63  jbe     short loc_180017EB8
0x180017e65  lea     rcx, [rbx+18h]; Buf1
0x180017e69  mov     r8, r15; Size
0x180017e6c  lea     rdx, qword_1800569A8; Buf2
0x180017e73  call    cs:__imp_memcmp
0x180017e79  test    eax, eax
0x180017e7b  jnz     short loc_180017E8C
0x180017e7d  mov     al, [rbx+2Dh]
0x180017e80  cmp     al, sil
0x180017e83  jz      short loc_180017EB8
0x180017e85  sub     al, 2
0x180017e87  cmp     al, sil
0x180017e8a  jbe     short loc_180017EB8
0x180017e8c  lea     rcx, [rbx+18h]; Buf1
0x180017e90  mov     r8, r15; Size
0x180017e93  lea     rdx, qword_180056998; Buf2
0x180017e9a  call    cs:__imp_memcmp
0x180017ea0  test    eax, eax
0x180017ea2  jnz     short loc_180017EB2
0x180017ea4  mov     al, [rbx+2Dh]
0x180017ea7  cmp     al, 0Ah
0x180017ea9  jz      short loc_180017EB8
0x180017eab  sub     al, 2
0x180017ead  cmp     al, sil
0x180017eb0  jbe     short loc_180017EB8
0x180017eb2  mov     eax, [rsp+68h+var_28]
0x180017eb6  jmp     short loc_180017EF8
0x180017eb8  lea     rax, aProcessid; "ProcessId"
0x180017ebf  mov     [rsp+68h+var_18], 0
0x180017ec8  mov     qword ptr [rsp+68h+var_20], rax
0x180017ecd  mov     rcx, rbx; this
0x180017ed0  lea     rax, [rsp+68h+var_28]
0x180017ed5  mov     qword ptr [rsp+68h+var_38], rax; unsigned int
0x180017eda  lea     rax, [rsp+68h+var_20]
0x180017edf  mov     qword ptr [rsp+68h+var_48], rax; unsigned int
0x180017ee4  call    ?TdhGetProperty@UnifiedPlatform@DiagnosticsHub@Microsoft@@YAKPEAU_EVENT_RECORD@@KPEAU_TDH_CONTEXT@@KPEAU_PROPERTY_DATA_DESCRIPTOR@@KPEAE@Z; Microsoft::DiagnosticsHub::UnifiedPlatform::TdhGetProperty(_EVENT_RECORD *,ulong,_TDH_CONTEXT *,ulong,_PROPERTY_DATA_DESCRIPTOR *,ulong,uchar *)
0x180017ee9  test    eax, eax
0x180017eeb  jnz     short loc_180017EF6
0x180017eed  mov     eax, [rsp+68h+var_28]
0x180017ef1  cmp     eax, 0FFFFFFFFh
0x180017ef4  jnz     short loc_180017EF8
0x180017ef6  xor     eax, eax
0x180017ef8  mov     rcx, [rsp+68h+var_10]
0x180017efd  xor     rcx, rsp; StackCookie
0x180017f00  call    __security_check_cookie
0x180017f05  lea     r11, [rsp+68h+var_8]
0x180017f0a  mov     rbx, [r11+18h]
0x180017f0e  mov     rsi, [r11+20h]
0x180017f12  mov     rdi, [r11+28h]
0x180017f16  mov     rsp, r11
0x180017f19  pop     r15
0x180017f1b  retn
```
