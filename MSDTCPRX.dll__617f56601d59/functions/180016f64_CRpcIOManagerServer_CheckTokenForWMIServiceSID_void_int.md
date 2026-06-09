# CRpcIOManagerServer::CheckTokenForWMIServiceSID(void *,int *)

- ea: `0x180016f64`
- end: `0x18001708e`
- name: `?CheckTokenForWMIServiceSID@CRpcIOManagerServer@@AEAAJPEAXPEAH@Z`
- size: `298`
- prototype: `__int64 __fastcall(PSID *this, void *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000d000`

## callees

- `0x180003cf0`
- `0x180016f64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016fcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016fcd`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180016fc3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180016fc3`

## string_xrefs

- `0x180016fa1`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180016ff4`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180017012`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x18001705c`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180017023`: `CheckTokenForWMIServiceSID - IsWMIService = %d`
- `0x180016fe2`: `Failed to check token membership for WMI SID!`
- `0x180016f80`: `CRpcIOManagerServer::CheckTokenForWMIServiceSID`

## pseudocode

```c
__int64 __fastcall CRpcIOManagerServer::CheckTokenForWMIServiceSID(PSID *this, void *a2, int *a3)
{
  unsigned int v3; // esi
  signed int LastError; // eax
  __int64 v9; // [rsp+28h] [rbp-50h]
  WINBOOL v10; // [rsp+38h] [rbp-40h]

  v3 = 0;
  TraceStringInline(
    1,
    6,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
    496,
    L"CRpcIOManagerServer::CheckTokenForWMIServiceSID",
    0,
    L"In");
  *a3 = 0;
  if ( !CheckTokenMembership(a2, this[13], a3) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    LODWORD(v9) = v3;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      504,
      L"CRpcIOManagerServer::CheckTokenForWMIServiceSID",
      v9,
      L"Failed to check token membership for WMI SID!");
  }
  v10 = *a3;
  TraceStringInline(
    1,
    3,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
    507,
    L"CRpcIOManagerServer::CheckTokenForWMIServiceSID",
    0,
    L"CheckTokenForWMIServiceSID - IsWMIService = %d",
    v10);
  TraceStringInline(
    1,
    6,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
    508,
    L"CRpcIOManagerServer::CheckTokenForWMIServiceSID",
    0,
    L"Out");
  return v3;
}

```

## disassembly

```asm
0x180016f64  push    rbx
0x180016f66  push    rsi
0x180016f67  push    rdi
0x180016f68  push    r13
0x180016f6a  push    r14
0x180016f6c  push    r15
0x180016f6e  sub     rsp, 48h
0x180016f72  xor     esi, esi
0x180016f74  lea     rax, aIn_0; "In"
0x180016f7b  mov     [rsp+78h+var_48], rax
0x180016f80  lea     r13, aCrpciomanagers_3; "CRpcIOManagerServer::CheckTokenForWMISe"...
0x180016f87  mov     r14, r8
0x180016f8a  mov     [rsp+78h+var_50], rsi
0x180016f8f  mov     rdi, rdx
0x180016f92  mov     [rsp+78h+var_58], r13
0x180016f97  mov     rbx, rcx
0x180016f9a  lea     r15d, [rsi+1]
0x180016f9e  mov     ecx, r15d
0x180016fa1  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180016fa8  mov     r9d, 1F0h
0x180016fae  lea     edx, [rsi+6]
0x180016fb1  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180016fb6  mov     [r14], esi
0x180016fb9  mov     r8, r14; IsMember
0x180016fbc  mov     rdx, [rbx+68h]; SidToCheck
0x180016fc0  mov     rcx, rdi; TokenHandle
0x180016fc3  call    cs:__imp_CheckTokenMembership
0x180016fc9  test    eax, eax
0x180016fcb  jnz     short loc_18001700F
0x180016fcd  call    cs:__imp_GetLastError
0x180016fd3  mov     esi, eax
0x180016fd5  test    eax, eax
0x180016fd7  jle     short loc_180016FE2
0x180016fd9  movzx   esi, ax
0x180016fdc  or      esi, 80070000h
0x180016fe2  lea     rax, aFailedToCheckT_0; "Failed to check token membership for WM"...
0x180016fe9  mov     r9d, 1F8h
0x180016fef  mov     [rsp+78h+var_48], rax
0x180016ff4  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180016ffb  mov     dword ptr [rsp+78h+var_50], esi
0x180016fff  mov     edx, r15d
0x180017002  mov     ecx, r15d
0x180017005  mov     [rsp+78h+var_58], r13
0x18001700a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001700f  mov     eax, [r14]
0x180017012  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180017019  mov     [rsp+78h+var_40], eax
0x18001701d  mov     r9d, 1FBh
0x180017023  lea     rax, aChecktokenforw; "CheckTokenForWMIServiceSID - IsWMIServi"...
0x18001702a  mov     edx, 3
0x18001702f  mov     [rsp+78h+var_48], rax
0x180017034  mov     ecx, r15d
0x180017037  mov     [rsp+78h+var_50], 0
0x180017040  mov     [rsp+78h+var_58], r13
0x180017045  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001704a  lea     rax, aOut; "Out"
0x180017051  mov     r9d, 1FCh
0x180017057  mov     [rsp+78h+var_48], rax
0x18001705c  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180017063  mov     [rsp+78h+var_50], 0
0x18001706c  mov     edx, 6
0x180017071  mov     ecx, r15d
0x180017074  mov     [rsp+78h+var_58], r13
0x180017079  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001707e  mov     eax, esi
0x180017080  add     rsp, 48h
0x180017084  pop     r15
0x180017086  pop     r14
0x180017088  pop     r13
0x18001708a  pop     rdi
0x18001708b  pop     rsi
0x18001708c  pop     rbx
0x18001708d  retn
```
