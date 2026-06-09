# FwAuthApps::Item(ushort *,INetFwAuthorizedApplication * *)

- ea: `0x180002540`
- end: `0x180002656`
- name: `?Item@FwAuthApps@@UEAAJPEAGPEAPEAUINetFwAuthorizedApplication@@@Z`
- size: `278`
- prototype: `int(FwAuthApps *__hidden this, unsigned __int16 *, struct INetFwAuthorizedApplication **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002540`
- `0x18000265c`
- `0x1800294b0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x1800025a6`
- `OLEAUT32!__imp_SysStringLen` at `0x1800025a6`
- `fwbase!FwBaseFree` at `0x180002615`
- `fwbase!FwBaseFree` at `0x180002615`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x1800025d3`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x1800025d3`
- `fwbase!FwReportReturnError` at `0x180002595`
- `fwbase!FwReportReturnError` at `0x18000262a`
- `fwbase!FwReportReturnError` at `0x180002595`
- `fwbase!FwReportReturnError` at `0x18000262a`

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
0x180002540  mov     [rsp+arg_18], rbx
0x180002545  push    rsi
0x180002546  push    rdi
0x180002547  push    r14
0x180002549  sub     rsp, 40h
0x18000254d  mov     rax, cs:__security_cookie
0x180002554  xor     rax, rsp
0x180002557  mov     [rsp+58h+var_20], rax
0x18000255c  mov     [rsp+58h+var_30], 0
0x180002565  mov     rdi, r8
0x180002568  mov     [rsp+58h+var_28], 0
0x180002570  mov     rbx, rdx
0x180002573  mov     [rsp+58h+var_38], 0
0x18000257c  mov     rsi, rcx
0x18000257f  lea     r14, aFwauthappsItem; "FwAuthApps::Item"
0x180002586  test    r8, r8
0x180002589  jnz     short loc_1800025A3
0x18000258b  mov     ebx, 80004003h
0x180002590  mov     edx, ebx
0x180002592  mov     rcx, r14
0x180002595  call    cs:__imp_FwReportReturnError
0x18000259c  nop     dword ptr [rax+rax+00h]
0x1800025a1  jmp     short loc_180002610
0x1800025a3  mov     rcx, rbx; pbstr
0x1800025a6  call    cs:__imp_SysStringLen
0x1800025ad  nop     dword ptr [rax+rax+00h]
0x1800025b2  test    eax, eax
0x1800025b4  jnz     short loc_1800025BF
0x1800025b6  mov     edx, 80070057h
0x1800025bb  mov     ebx, edx
0x1800025bd  jmp     short loc_180002592
0x1800025bf  lea     r8, [rsp+58h+var_28]
0x1800025c4  mov     qword ptr [rdi], 0
0x1800025cb  lea     rdx, [rsp+58h+var_30]
0x1800025d0  mov     rcx, rbx
0x1800025d3  call    cs:__imp_FwGetExpandedCanonicalLongPathName
0x1800025da  nop     dword ptr [rax+rax+00h]
0x1800025df  mov     ebx, eax
0x1800025e1  test    eax, eax
0x1800025e3  jns     short loc_1800025E9
0x1800025e5  mov     edx, eax
0x1800025e7  jmp     short loc_180002592
0x1800025e9  cmp     [rsp+58h+var_28], 0
0x1800025ee  jz      short loc_1800025B6
0x1800025f0  mov     rdx, [rsp+58h+var_30]
0x1800025f5  lea     r8, [rsp+58h+var_38]
0x1800025fa  mov     ecx, [rsi+18h]
0x1800025fd  call    ?CreateInstance@FwAuthApp@@SAJW4_tag_FW_PROFILE_TYPE@@PEBGPEAPEAV1@@Z; FwAuthApp::CreateInstance(_tag_FW_PROFILE_TYPE,ushort const *,FwAuthApp * *)
0x180002602  mov     ebx, eax
0x180002604  test    eax, eax
0x180002606  js      short loc_1800025E5
0x180002608  mov     rax, [rsp+58h+var_38]
0x18000260d  mov     [rdi], rax
0x180002610  mov     rcx, [rsp+58h+var_30]
0x180002615  call    cs:__imp_FwBaseFree
0x18000261c  nop     dword ptr [rax+rax+00h]
0x180002621  test    ebx, ebx
0x180002623  jns     short loc_180002638
0x180002625  mov     edx, ebx
0x180002627  mov     rcx, r14
0x18000262a  call    cs:__imp_FwReportReturnError
0x180002631  nop     dword ptr [rax+rax+00h]
0x180002636  mov     ebx, eax
0x180002638  mov     eax, ebx
0x18000263a  mov     rcx, [rsp+58h+var_20]
0x18000263f  xor     rcx, rsp; StackCookie
0x180002642  call    __security_check_cookie
0x180002647  mov     rbx, [rsp+58h+arg_18]
0x18000264c  add     rsp, 40h
0x180002650  pop     r14
0x180002652  pop     rdi
0x180002653  pop     rsi
0x180002654  retn
```
