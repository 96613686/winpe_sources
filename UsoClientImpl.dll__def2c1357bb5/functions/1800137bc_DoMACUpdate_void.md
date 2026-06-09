# DoMACUpdate(void)

- ea: `0x1800137bc`
- end: `0x1800138ac`
- name: `?DoMACUpdate@@YAXXZ`
- size: `240`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800150a0`

## callees

- `0x18000ba08`
- `0x18000f0a4`
- `0x1800137bc`
- `0x180034a30`
- `0x18003a74c`
- `0x180056500`
- `0x18005c5e0`

## string_xrefs

- `0x180013876`: `MACUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void DoMACUpdate(void)
{
  _QWORD *DockedClient; // rax
  int v1; // eax
  int v2; // [rsp+20h] [rbp-19h]
  __int64 v3; // [rsp+50h] [rbp+17h] BYREF
  int v4[4]; // [rsp+58h] [rbp+1Fh] BYREF
  int v5[4]; // [rsp+68h] [rbp+2Fh]
  int v6; // [rsp+78h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  *(_OWORD *)v4 = 0;
  *(_OWORD *)v5 = 0;
  v6 = 0;
  DockedClient = (_QWORD *)Windows::DockedHelpers::GetDockedClient(&v3);
  v1 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*DockedClient + 56LL))(*DockedClient, v4);
  if ( v1 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x41E,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
      (const char *)(unsigned int)v1,
      v2);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  ClientCoreTelemetry::MACUpdateResult(
    v4[0] != 0,
    v4[1] != 0,
    v4[2],
    v4[3] != 0,
    v5[0] != 0,
    v5[1],
    v5[2],
    v5[3],
    v6 != 0);
  ReportUOWorkCompleted(L"MACUpdate", v4[0]);
}

```

## disassembly

```asm
0x1800137bc  push    rbp
0x1800137be  lea     rbp, [rsp-57h]
0x1800137c3  sub     rsp, 90h
0x1800137ca  mov     rax, cs:__security_cookie
0x1800137d1  xor     rax, rsp
0x1800137d4  mov     [rbp+57h+var_10], rax
0x1800137d8  xorps   xmm0, xmm0
0x1800137db  xor     eax, eax
0x1800137dd  movups  xmmword ptr [rbp+57h+var_38], xmm0
0x1800137e1  movups  xmmword ptr [rbp+57h+var_28], xmm0
0x1800137e5  mov     [rbp+57h+var_18], eax
0x1800137e8  lea     rcx, [rbp+57h+var_40]
0x1800137ec  call    ?GetDockedClient@DockedHelpers@Windows@@YA?AV?$com_ptr_t@UIDockedClient2@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::DockedHelpers::GetDockedClient(void)
0x1800137f1  nop
0x1800137f2  mov     rcx, [rax]
0x1800137f5  mov     rax, [rcx]
0x1800137f8  lea     rdx, [rbp+57h+var_38]
0x1800137fc  mov     rax, [rax+38h]
0x180013800  call    _guard_dispatch_icall
0x180013805  mov     rcx, [rbp+5Fh]; this
0x180013809  test    eax, eax
0x18001380b  js      loc_180013897
0x180013811  mov     rcx, [rbp+57h+var_40]
0x180013815  test    rcx, rcx
0x180013818  jz      short loc_180013827
0x18001381a  mov     rax, [rcx]
0x18001381d  mov     rax, [rax+10h]
0x180013821  call    _guard_dispatch_icall
0x180013826  nop
0x180013827  cmp     [rbp+57h+var_18], 0
0x18001382b  setnz   al
0x18001382e  cmp     [rbp+57h+var_28], 0
0x180013832  setnz   r8b
0x180013836  cmp     [rbp+57h+var_38+0Ch], 0
0x18001383a  setnz   r9b; bool
0x18001383e  cmp     [rbp+57h+var_38+4], 0
0x180013842  setnz   dl; bool
0x180013845  cmp     [rbp+57h+var_38], 0
0x180013849  setnz   cl; bool
0x18001384c  mov     [rsp+90h+var_50], al; bool
0x180013850  mov     eax, [rbp+57h+var_28+0Ch]
0x180013853  mov     [rsp+90h+var_58], eax; int
0x180013857  mov     eax, [rbp+57h+var_28+8]
0x18001385a  mov     [rsp+90h+var_60], eax; int
0x18001385e  mov     eax, [rbp+57h+var_28+4]
0x180013861  mov     [rsp+90h+var_68], eax; int
0x180013865  mov     [rsp+90h+var_70], r8b; bool
0x18001386a  mov     r8d, [rbp+57h+var_38+8]; int
0x18001386e  call    ?MACUpdateResult@ClientCoreTelemetry@@SAX_N0H00HJJ0@Z; ClientCoreTelemetry::MACUpdateResult(bool,bool,int,bool,bool,int,long,long,bool)
0x180013873  mov     edx, [rbp+57h+var_38]; int
0x180013876  lea     rcx, aMacupdate; "MACUpdate"
0x18001387d  call    ?ReportUOWorkCompleted@@YAXPEB_WH@Z; ReportUOWorkCompleted(wchar_t const *,int)
0x180013882  mov     rcx, [rbp+57h+var_10]
0x180013886  xor     rcx, rsp; StackCookie
0x180013889  call    __security_check_cookie
0x18001388e  add     rsp, 90h
0x180013895  pop     rbp
0x180013896  retn
0x180013897  mov     r9d, eax; char *
0x18001389a  lea     r8, aCW1SSrcOrchest_3; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x1800138a1  mov     edx, 41Eh; void *
0x1800138a6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
