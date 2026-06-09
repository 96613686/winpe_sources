# JobHelper::CreateDOJob(ushort const *,IBackgroundCopyManager * *,IBackgroundCopyJob * *,_GUID *)

- ea: `0x140018a68`
- end: `0x140018b38`
- name: `?CreateDOJob@JobHelper@@SAJPEBGPEAPEAUIBackgroundCopyManager@@PEAPEAUIBackgroundCopyJob@@PEAU_GUID@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPVOID *, IUnknown **, struct _GUID *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000cb14`
- `0x140010a2c`

## callees

- `0x1400056a4`
- `0x140018a68`
- `0x14001c010`

## import_xrefs

- `ole32!CoSetProxyBlanket` at `0x140018b17`
- `ole32!CoSetProxyBlanket` at `0x140018b17`
- `ole32!CoCreateInstance` at `0x140018a93`
- `ole32!CoCreateInstance` at `0x140018a93`

## pseudocode

```c
__int64 __fastcall JobHelper::CreateDOJob(const unsigned __int16 *a1, LPVOID *a2, IUnknown **a3, struct _GUID *a4)
{
  HRESULT Instance; // ebx
  __int64 v8; // rdx
  int ppv; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  Instance = CoCreateInstance(
               &GUID_5b99fa76_721c_423c_adac_56d03c8a8007,
               0,
               4u,
               &GUID_5ce34c0d_0dc9_4c1f_897c_daa1b78cee7c,
               a2);
  if ( Instance < 0 )
  {
    v8 = 52;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"admin\\enterprisemgmt\\desktopappcsps\\sharedlib\\jobhelper.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    return (unsigned int)Instance;
  }
  ppv = (int)a3;
  Instance = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD, struct _GUID *))(*(_QWORD *)*a2 + 24LL))(
               *a2,
               L"MDM EDAM Job",
               0,
               a4);
  if ( Instance < 0 )
  {
    v8 = 59;
    goto LABEL_3;
  }
  Instance = CoSetProxyBlanket(*a3, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0x40u);
  if ( Instance < 0 )
  {
    v8 = 62;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x140018a68  push    rbx
0x140018a6a  push    rbp
0x140018a6b  push    rsi
0x140018a6c  push    rdi
0x140018a6d  sub     rsp, 48h
0x140018a71  mov     rsi, rdx
0x140018a74  mov     [rsp+68h+ppv], rdx; int
0x140018a79  xor     edx, edx; pUnkOuter
0x140018a7b  lea     rcx, _GUID_5b99fa76_721c_423c_adac_56d03c8a8007; rclsid
0x140018a82  mov     rbp, r9
0x140018a85  mov     rdi, r8
0x140018a88  lea     r9, _GUID_5ce34c0d_0dc9_4c1f_897c_daa1b78cee7c; riid
0x140018a8f  lea     r8d, [rdx+4]; dwClsContext
0x140018a93  call    cs:__imp_CoCreateInstance
0x140018a99  mov     ebx, eax
0x140018a9b  test    eax, eax
0x140018a9d  jns     short loc_140018ABC
0x140018a9f  mov     edx, 34h ; '4'; void *
0x140018aa4  mov     rcx, [rsp+68h]; this
0x140018aa9  lea     r8, aAdminEnterpris_0; "admin\\enterprisemgmt\\desktopappcsps\\"...
0x140018ab0  mov     r9d, ebx; char *
0x140018ab3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018ab8  mov     eax, ebx
0x140018aba  jmp     short loc_140018B2F
0x140018abc  mov     rcx, [rsi]
0x140018abf  lea     rdx, aMdmEdamJob; "MDM EDAM Job"
0x140018ac6  mov     r9, rbp
0x140018ac9  mov     [rsp+68h+ppv], rdi
0x140018ace  xor     r8d, r8d
0x140018ad1  mov     rax, [rcx]
0x140018ad4  mov     rax, [rax+18h]
0x140018ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018add  mov     ebx, eax
0x140018adf  test    eax, eax
0x140018ae1  jns     short loc_140018AEA
0x140018ae3  mov     edx, 3Bh ; ';'
0x140018ae8  jmp     short loc_140018AA4
0x140018aea  mov     rcx, [rdi]; pProxy
0x140018aed  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x140018af0  mov     [rsp+68h+dwCapabilities], 40h ; '@'; dwCapabilities
0x140018af8  mov     r8d, edx; dwAuthzSvc
0x140018afb  mov     [rsp+68h+pAuthInfo], 0; pAuthInfo
0x140018b04  xor     r9d, r9d; pServerPrincName
0x140018b07  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x140018b0f  mov     dword ptr [rsp+68h+ppv], 0; dwAuthnLevel
0x140018b17  call    cs:__imp_CoSetProxyBlanket
0x140018b1d  mov     ebx, eax
0x140018b1f  test    eax, eax
0x140018b21  jns     short loc_140018B2D
0x140018b23  mov     edx, 3Eh ; '>'
0x140018b28  jmp     loc_140018AA4
0x140018b2d  xor     eax, eax
0x140018b2f  add     rsp, 48h
0x140018b33  pop     rdi
0x140018b34  pop     rsi
0x140018b35  pop     rbp
0x140018b36  pop     rbx
0x140018b37  retn
```
