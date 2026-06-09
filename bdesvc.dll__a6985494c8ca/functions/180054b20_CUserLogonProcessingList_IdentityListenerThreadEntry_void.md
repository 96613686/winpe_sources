# CUserLogonProcessingList::IdentityListenerThreadEntry(void *)

- ea: `0x180054b20`
- end: `0x180054c0e`
- name: `?IdentityListenerThreadEntry@CUserLogonProcessingList@@KAIPEAX@Z`
- size: `238`
- prototype: `unsigned int __fastcall(CUserLogonProcessingList *this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180009c30`
- `0x180009f60`
- `0x180023c1c`
- `0x180026278`
- `0x18002b6ac`
- `0x180054b20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180054bef`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180054bef`

## string_xrefs

- `0x180054b77`: `ComInitialize`
- `0x180054bbd`: `IdentityListenerThread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUserLogonProcessingList::IdentityListenerThreadEntry(CUserLogonProcessingList *this)
{
  unsigned int v2; // eax
  int v3; // ebx
  const char *v4; // rax
  __int64 v5; // rdx
  unsigned int v6; // eax
  BdeSvcWorkTracking *v7; // rcx
  const char *v9; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v11; // [rsp+40h] [rbp+8h] BYREF

  v11 = 0;
  v2 = CInitializeCom::Initialize((CInitializeCom *)&v11);
  v3 = v2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 250, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v2);
  if ( v3 < 0 )
  {
    v4 = "ComInitialize";
    v5 = 3550;
LABEL_11:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v5,
      (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
      (const char *)(unsigned int)v3,
      (int)v4,
      v9);
    goto LABEL_12;
  }
  v6 = CUserLogonProcessingList::IdentityListenerThread(this);
  v3 = v6;
  v7 = (BdeSvcWorkTracking *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 251, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v6);
  if ( v3 < 0 )
  {
    v4 = "IdentityListenerThread";
    v5 = 3551;
    goto LABEL_11;
  }
LABEL_12:
  BdeSvcWorkTracking::FinishWorkImpl(v7);
  if ( v11 )
    CoUninitialize();
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180054b20  mov     rax, rsp
0x180054b23  mov     [rax+10h], rbx
0x180054b27  mov     [rax+18h], rsi
0x180054b2b  push    rdi
0x180054b2c  sub     rsp, 30h
0x180054b30  mov     rdi, rcx
0x180054b33  mov     byte ptr [rax+8], 0
0x180054b37  lea     rcx, [rax+8]; this
0x180054b3b  call    ?Initialize@CInitializeCom@@QEAAJXZ; CInitializeCom::Initialize(void)
0x180054b40  mov     ebx, eax
0x180054b42  lea     rsi, WPP_GLOBAL_Control
0x180054b49  mov     rcx, cs:WPP_GLOBAL_Control
0x180054b50  cmp     rcx, rsi
0x180054b53  jz      short loc_180054B73
0x180054b55  test    byte ptr [rcx+1Ch], 40h
0x180054b59  jz      short loc_180054B73
0x180054b5b  mov     edx, 0FAh
0x180054b60  mov     r9d, eax
0x180054b63  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x180054b6a  mov     rcx, [rcx+10h]
0x180054b6e  call    WPP_SF_d
0x180054b73  test    ebx, ebx
0x180054b75  jns     short loc_180054B85
0x180054b77  lea     rax, aCominitialize; "ComInitialize"
0x180054b7e  mov     edx, 0DDEh
0x180054b83  jmp     short loc_180054BC9
0x180054b85  mov     rcx, rdi; this
0x180054b88  call    ?IdentityListenerThread@CUserLogonProcessingList@@IEAAJXZ; CUserLogonProcessingList::IdentityListenerThread(void)
0x180054b8d  mov     ebx, eax
0x180054b8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180054b96  cmp     rcx, rsi
0x180054b99  jz      short loc_180054BB9
0x180054b9b  test    byte ptr [rcx+1Ch], 40h
0x180054b9f  jz      short loc_180054BB9
0x180054ba1  mov     edx, 0FBh
0x180054ba6  mov     r9d, eax
0x180054ba9  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x180054bb0  mov     rcx, [rcx+10h]
0x180054bb4  call    WPP_SF_d
0x180054bb9  test    ebx, ebx
0x180054bbb  jns     short loc_180054BE2
0x180054bbd  lea     rax, aIdentitylisten; "IdentityListenerThread"
0x180054bc4  mov     edx, 0DDFh; void *
0x180054bc9  mov     qword ptr [rsp+38h+var_18], rax; int
0x180054bce  mov     r9d, ebx; char *
0x180054bd1  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x180054bd8  mov     rcx, [rsp+38h]; this
0x180054bdd  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180054be2  call    ?FinishWorkImpl@BdeSvcWorkTracking@@AEAAXXZ; BdeSvcWorkTracking::FinishWorkImpl(void)
0x180054be7  nop
0x180054be8  cmp     [rsp+38h+arg_0], 0
0x180054bed  jz      short loc_180054BFB
0x180054bef  call    cs:__imp_CoUninitialize
0x180054bf6  nop     dword ptr [rax+rax+00h]
0x180054bfb  mov     eax, ebx
0x180054bfd  mov     rbx, [rsp+38h+arg_8]
0x180054c02  mov     rsi, [rsp+38h+arg_10]
0x180054c07  add     rsp, 30h
0x180054c0b  pop     rdi
0x180054c0c  retn
```
