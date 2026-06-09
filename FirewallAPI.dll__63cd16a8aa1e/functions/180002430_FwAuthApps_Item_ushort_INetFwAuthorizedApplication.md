# FwAuthApps::Item(ushort *,INetFwAuthorizedApplication * *)

- ea: `0x180002430`
- end: `0x180002527`
- name: `?Item@FwAuthApps@@UEAAJPEAGPEAPEAUINetFwAuthorizedApplication@@@Z`
- size: `247`
- prototype: `int(FwAuthApps *__hidden this, unsigned __int16 *, struct INetFwAuthorizedApplication **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002430`
- `0x180002530`
- `0x1800277b0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180002490`
- `OLEAUT32!__imp_SysStringLen` at `0x180002490`
- `fwbase!FwBaseFree` at `0x1800024f3`
- `fwbase!FwBaseFree` at `0x1800024f3`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x1800024b7`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x1800024b7`
- `fwbase!FwReportReturnError` at `0x180002485`
- `fwbase!FwReportReturnError` at `0x180002502`
- `fwbase!FwReportReturnError` at `0x180002485`
- `fwbase!FwReportReturnError` at `0x180002502`

## pseudocode

```c
__int64 __fastcall FwAuthApps::Item(FwAuthApps *this, unsigned __int16 *a2, struct INetFwAuthorizedApplication **a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  int ExpandedCanonicalLongPathName; // eax
  struct INetFwAuthorizedApplication *v10; // [rsp+20h] [rbp-38h] BYREF
  __int64 v11; // [rsp+28h] [rbp-30h] BYREF
  int v12; // [rsp+30h] [rbp-28h] BYREF

  v11 = 0;
  v12 = 0;
  v10 = 0;
  if ( !a3 )
  {
    v6 = -2147467261;
    v7 = 2147500035LL;
LABEL_3:
    FwReportReturnError("FwAuthApps::Item", v7);
    goto LABEL_11;
  }
  if ( !SysStringLen(a2) )
  {
LABEL_5:
    v7 = 2147942487LL;
    v6 = -2147024809;
    goto LABEL_3;
  }
  *a3 = 0;
  ExpandedCanonicalLongPathName = FwGetExpandedCanonicalLongPathName(a2, &v11, &v12);
  v6 = ExpandedCanonicalLongPathName;
  if ( ExpandedCanonicalLongPathName < 0 )
    goto LABEL_7;
  if ( !v12 )
    goto LABEL_5;
  ExpandedCanonicalLongPathName = FwAuthApp::CreateInstance(*((unsigned int *)this + 6), v11, &v10);
  v6 = ExpandedCanonicalLongPathName;
  if ( ExpandedCanonicalLongPathName < 0 )
  {
LABEL_7:
    v7 = (unsigned int)ExpandedCanonicalLongPathName;
    goto LABEL_3;
  }
  *a3 = v10;
LABEL_11:
  FwBaseFree(v11);
  if ( v6 < 0 )
    return (unsigned int)FwReportReturnError("FwAuthApps::Item", (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002430  mov     [rsp+arg_18], rbx
0x180002435  push    rsi
0x180002436  push    rdi
0x180002437  push    r14
0x180002439  sub     rsp, 40h
0x18000243d  mov     rax, cs:__security_cookie
0x180002444  xor     rax, rsp
0x180002447  mov     [rsp+58h+var_20], rax
0x18000244c  mov     [rsp+58h+var_30], 0
0x180002455  mov     rdi, r8
0x180002458  mov     [rsp+58h+var_28], 0
0x180002460  mov     rbx, rdx
0x180002463  mov     [rsp+58h+var_38], 0
0x18000246c  mov     rsi, rcx
0x18000246f  lea     r14, aFwauthappsItem; "FwAuthApps::Item"
0x180002476  test    r8, r8
0x180002479  jnz     short loc_18000248D
0x18000247b  mov     ebx, 80004003h
0x180002480  mov     edx, ebx
0x180002482  mov     rcx, r14
0x180002485  call    cs:__imp_FwReportReturnError
0x18000248b  jmp     short loc_1800024EE
0x18000248d  mov     rcx, rbx; pbstr
0x180002490  call    cs:__imp_SysStringLen
0x180002496  test    eax, eax
0x180002498  jnz     short loc_1800024A3
0x18000249a  mov     edx, 80070057h
0x18000249f  mov     ebx, edx
0x1800024a1  jmp     short loc_180002482
0x1800024a3  lea     r8, [rsp+58h+var_28]
0x1800024a8  mov     qword ptr [rdi], 0
0x1800024af  lea     rdx, [rsp+58h+var_30]
0x1800024b4  mov     rcx, rbx
0x1800024b7  call    cs:__imp_FwGetExpandedCanonicalLongPathName
0x1800024bd  mov     ebx, eax
0x1800024bf  test    eax, eax
0x1800024c1  jns     short loc_1800024C7
0x1800024c3  mov     edx, eax
0x1800024c5  jmp     short loc_180002482
0x1800024c7  cmp     [rsp+58h+var_28], 0
0x1800024cc  jz      short loc_18000249A
0x1800024ce  mov     rdx, [rsp+58h+var_30]
0x1800024d3  lea     r8, [rsp+58h+var_38]
0x1800024d8  mov     ecx, [rsi+18h]
0x1800024db  call    ?CreateInstance@FwAuthApp@@SAJW4_tag_FW_PROFILE_TYPE@@PEBGPEAPEAV1@@Z; FwAuthApp::CreateInstance(_tag_FW_PROFILE_TYPE,ushort const *,FwAuthApp * *)
0x1800024e0  mov     ebx, eax
0x1800024e2  test    eax, eax
0x1800024e4  js      short loc_1800024C3
0x1800024e6  mov     rax, [rsp+58h+var_38]
0x1800024eb  mov     [rdi], rax
0x1800024ee  mov     rcx, [rsp+58h+var_30]
0x1800024f3  call    cs:__imp_FwBaseFree
0x1800024f9  test    ebx, ebx
0x1800024fb  jns     short loc_18000250A
0x1800024fd  mov     edx, ebx
0x1800024ff  mov     rcx, r14
0x180002502  call    cs:__imp_FwReportReturnError
0x180002508  mov     ebx, eax
0x18000250a  mov     eax, ebx
0x18000250c  mov     rcx, [rsp+58h+var_20]
0x180002511  xor     rcx, rsp; StackCookie
0x180002514  call    __security_check_cookie
0x180002519  mov     rbx, [rsp+58h+arg_18]
0x18000251e  add     rsp, 40h
0x180002522  pop     r14
0x180002524  pop     rdi
0x180002525  pop     rsi
0x180002526  retn
```
