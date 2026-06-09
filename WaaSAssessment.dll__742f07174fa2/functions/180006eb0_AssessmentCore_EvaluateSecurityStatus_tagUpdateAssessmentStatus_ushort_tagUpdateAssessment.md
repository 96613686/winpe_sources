# AssessmentCore::EvaluateSecurityStatus(tagUpdateAssessmentStatus &,ushort *,tagUpdateAssessment &)

- ea: `0x180006eb0`
- end: `0x180006f60`
- name: `?EvaluateSecurityStatus@AssessmentCore@@MEAAJAEAW4tagUpdateAssessmentStatus@@PEAGAEAUtagUpdateAssessment@@@Z`
- size: `176`
- prototype: `int(AssessmentCore *__hidden this, enum tagUpdateAssessmentStatus *, unsigned __int16 *, struct tagUpdateAssessment *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006eb0`
- `0x18001752c`
- `0x180018b8c`

## string_xrefs

- `0x180006ee6`: `Device is secure according to update status`
- `0x180006f23`: `Device is secure according to update status`
- `0x180006f3d`: `EvaluateSecurityStatus Failure: 0x%x`

## pseudocode

```c
__int64 __fastcall AssessmentCore::EvaluateSecurityStatus(
        AssessmentCore *this,
        enum tagUpdateAssessmentStatus *a2,
        unsigned __int16 *a3,
        struct tagUpdateAssessment *a4)
{
  bool v5; // zf
  unsigned int v7; // edi
  int v8; // eax
  enum tagUpdateAssessmentStatus status; // eax
  int v11; // [rsp+38h] [rbp+10h] BYREF
  int v12; // [rsp+48h] [rbp+20h] BYREF

  *a2 = UpdateAssessmentStatus_NotLatestUnknown;
  v5 = a4->status == UpdateAssessmentStatus_Latest;
  v11 = 0;
  v12 = 0;
  if ( v5 )
  {
    v7 = 0;
    LogLevel(4u, L"Device is secure according to update status");
    *a2 = UpdateAssessmentStatus_Latest;
  }
  else
  {
    v8 = IsOSVersionPresentInList(a3, (unsigned __int16 *)this + 888, &v11, &v12);
    v7 = v8;
    if ( v8 < 0 )
    {
      LogLevel(2u, L"EvaluateSecurityStatus Failure: 0x%x", (unsigned int)v8);
    }
    else
    {
      if ( v11 )
      {
        LogLevel(4u, L"Device is secure according to update status");
        status = UpdateAssessmentStatus_Latest;
      }
      else
      {
        status = a4->status;
      }
      *a2 = status;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180006eb0  mov     [rsp+arg_0], rbx
0x180006eb5  mov     [rsp+arg_10], rsi
0x180006eba  push    rdi
0x180006ebb  sub     rsp, 20h
0x180006ebf  mov     dword ptr [rdx], 0Ah
0x180006ec5  mov     rsi, r9
0x180006ec8  cmp     dword ptr [r9], 0
0x180006ecc  mov     rax, r8
0x180006ecf  mov     rbx, rdx
0x180006ed2  mov     [rsp+28h+arg_8], 0
0x180006eda  mov     [rsp+28h+arg_18], 0
0x180006ee2  jnz     short loc_180006EF9
0x180006ee4  xor     edi, edi
0x180006ee6  lea     rdx, aDeviceIsSecure; "Device is secure according to update st"...
0x180006eed  lea     ecx, [rdi+4]; unsigned __int8
0x180006ef0  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180006ef5  mov     [rbx], edi
0x180006ef7  jmp     short loc_180006F4E
0x180006ef9  lea     rdx, [rcx+6F0h]; unsigned __int16 *
0x180006f00  mov     rcx, rax; unsigned __int16 *
0x180006f03  lea     r9, [rsp+28h+arg_18]; int *
0x180006f08  lea     r8, [rsp+28h+arg_8]; int *
0x180006f0d  call    ?IsOSVersionPresentInList@@YAJPEBG0AEAH1@Z; IsOSVersionPresentInList(ushort const *,ushort const *,int &,int &)
0x180006f12  mov     edi, eax
0x180006f14  test    eax, eax
0x180006f16  js      short loc_180006F3A
0x180006f18  cmp     [rsp+28h+arg_8], 0
0x180006f1d  jnz     short loc_180006F23
0x180006f1f  mov     eax, [rsi]
0x180006f21  jmp     short loc_180006F36
0x180006f23  lea     rdx, aDeviceIsSecure; "Device is secure according to update st"...
0x180006f2a  mov     ecx, 4; unsigned __int8
0x180006f2f  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180006f34  xor     eax, eax
0x180006f36  mov     [rbx], eax
0x180006f38  jmp     short loc_180006F4E
0x180006f3a  mov     r8d, eax
0x180006f3d  lea     rdx, aEvaluatesecuri; "EvaluateSecurityStatus Failure: 0x%x"
0x180006f44  mov     ecx, 2; unsigned __int8
0x180006f49  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180006f4e  mov     rbx, [rsp+28h+arg_0]
0x180006f53  mov     eax, edi
0x180006f55  mov     rsi, [rsp+28h+arg_10]
0x180006f5a  add     rsp, 20h
0x180006f5e  pop     rdi
0x180006f5f  retn
```
