# OOBEBrokerManager::CreateOOBEUserObject(_GUID const &,_GUID const &,void * *)

- ea: `0x18000b6c0`
- end: `0x18000b75b`
- name: `?CreateOOBEUserObject@OOBEBrokerManager@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `155`
- prototype: `__int64 __fastcall(OOBEBrokerManager *this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007134`
- `0x18000b6c0`
- `0x18000b770`
- `0x18000bef8`
- `0x18000c150`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b709`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b709`

## string_xrefs

- `0x18000b73d`: `shell\oobe\user\dll\oobebrokermanager.cpp`

## pseudocode

```c
__int64 __fastcall OOBEBrokerManager::CreateOOBEUserObject(
        OOBEBrokerManager *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT OOBEUserObjectForceBroker; // ebx
  __int64 v9; // rdx
  int ppv; // [rsp+20h] [rbp-48h]
  unsigned __int8 v12[56]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v12[0] = 0;
  if ( IsUserOOBE() || (int)IsCandidateUser(v12) >= 0 && v12[0] )
  {
    OOBEUserObjectForceBroker = OOBEBrokerManager::CreateOOBEUserObjectForceBroker(this, a2, a3, a4);
    if ( OOBEUserObjectForceBroker < 0 )
    {
      v9 = 131;
      goto LABEL_8;
    }
  }
  else
  {
    OOBEUserObjectForceBroker = CoCreateInstance(a2, 0, 1u, a3, a4);
    if ( OOBEUserObjectForceBroker < 0 )
    {
      v9 = 135;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"shell\\oobe\\user\\dll\\oobebrokermanager.cpp",
        (const char *)(unsigned int)OOBEUserObjectForceBroker,
        ppv);
      return (unsigned int)OOBEUserObjectForceBroker;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000b6c0  push    rbx
0x18000b6c2  push    rbp
0x18000b6c3  push    rsi
0x18000b6c4  push    rdi
0x18000b6c5  sub     rsp, 48h
0x18000b6c9  mov     rbx, r9
0x18000b6cc  mov     [rsp+68h+var_38], 0
0x18000b6d1  mov     rdi, r8
0x18000b6d4  mov     rsi, rdx
0x18000b6d7  mov     rbp, rcx
0x18000b6da  call    ?IsUserOOBE@@YA_NXZ; IsUserOOBE(void)
0x18000b6df  test    al, al
0x18000b6e1  jnz     short loc_18000B71C
0x18000b6e3  lea     rcx, [rsp+68h+var_38]; unsigned __int8 *
0x18000b6e8  call    ?IsCandidateUser@@YAJPEAE@Z; IsCandidateUser(uchar *)
0x18000b6ed  test    eax, eax
0x18000b6ef  js      short loc_18000B6F8
0x18000b6f1  cmp     [rsp+68h+var_38], 0
0x18000b6f6  jnz     short loc_18000B71C
0x18000b6f8  xor     edx, edx; pUnkOuter
0x18000b6fa  mov     qword ptr [rsp+68h+ppv], rbx; ppv
0x18000b6ff  mov     r9, rdi; riid
0x18000b702  mov     rcx, rsi; rclsid
0x18000b705  lea     r8d, [rdx+1]; dwClsContext
0x18000b709  call    cs:__imp_CoCreateInstance
0x18000b70f  mov     ebx, eax
0x18000b711  test    eax, eax
0x18000b713  jns     short loc_18000B750
0x18000b715  mov     edx, 87h
0x18000b71a  jmp     short loc_18000B738
0x18000b71c  mov     r9, rbx; void **
0x18000b71f  mov     r8, rdi; struct _GUID *
0x18000b722  mov     rdx, rsi; struct _GUID *
0x18000b725  mov     rcx, rbp; this
0x18000b728  call    ?CreateOOBEUserObjectForceBroker@OOBEBrokerManager@@UEAAJAEBU_GUID@@0PEAPEAX@Z; OOBEBrokerManager::CreateOOBEUserObjectForceBroker(_GUID const &,_GUID const &,void * *)
0x18000b72d  mov     ebx, eax
0x18000b72f  test    eax, eax
0x18000b731  jns     short loc_18000B750
0x18000b733  mov     edx, 83h; void *
0x18000b738  mov     rcx, [rsp+68h]; this
0x18000b73d  lea     r8, aShellOobeUserD; "shell\\oobe\\user\\dll\\oobebrokermanag"...
0x18000b744  mov     r9d, ebx; char *
0x18000b747  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b74c  mov     eax, ebx
0x18000b74e  jmp     short loc_18000B752
0x18000b750  xor     eax, eax
0x18000b752  add     rsp, 48h
0x18000b756  pop     rdi
0x18000b757  pop     rsi
0x18000b758  pop     rbp
0x18000b759  pop     rbx
0x18000b75a  retn
```
