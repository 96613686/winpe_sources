# LockDownPolicyTask::GetGroupPolicyObject(PolicyType)

- ea: `0x1800233cc`
- end: `0x180023547`
- name: `?GetGroupPolicyObject@LockDownPolicyTask@@AEAA?AV?$ComPtr@UIGroupPolicyObject2@@@WRL@Microsoft@@W4PolicyType@@@Z`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180022f1c`

## callees

- `0x180008bbc`
- `0x18001094c`
- `0x1800233cc`
- `0x180023720`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023412`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800234ac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023412`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800234ac`

## string_xrefs

- `0x180023424`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\lockdownpolicytask.cpp`
- `0x180023456`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\lockdownpolicytask.cpp`
- `0x1800234be`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\lockdownpolicytask.cpp`
- `0x180023505`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\lockdownpolicytask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LPVOID *__fastcall LockDownPolicyTask::GetGroupPolicyObject(LockDownPolicyTask *this, LPVOID *a2, __int64 a3)
{
  LPVOID *v5; // rbx
  HRESULT v6; // eax
  int v7; // eax
  LPVOID v8; // rcx
  LPVOID *v9; // r14
  HRESULT Instance; // eax
  LPVOID v11; // rdi
  __int64 (__fastcall *v12)(LPVOID, const unsigned __int16 *, __int64); // rbx
  const unsigned __int16 *UserSid; // rax
  int v14; // eax
  int ppv; // [rsp+20h] [rbp-48h]
  int ppva; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( (_DWORD)a3 )
  {
    if ( (_DWORD)a3 != 1 )
    {
      *a2 = 0;
      return a2;
    }
    v9 = (LPVOID *)((char *)this + 104);
    if ( !*((_QWORD *)this + 13) )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 104, a2, a3);
      Instance = CoCreateInstance(&CLSID_GroupPolicyObject, 0, 1u, &IID_IGroupPolicyObject2, v9);
      if ( Instance < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x33,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\lockdownpolicytask.cpp",
          (const char *)(unsigned int)Instance,
          ppva);
      v11 = *v9;
      v12 = *(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, __int64))(*(_QWORD *)*v9 + 168LL);
      UserSid = LockDownPolicyTask::GetUserSid(this);
      v14 = v12(v11, UserSid, 1);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x34,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\lockdownpolicytask.cpp",
          (const char *)(unsigned int)v14,
          ppva);
    }
    v8 = *v9;
    *a2 = *v9;
  }
  else
  {
    v5 = (LPVOID *)((char *)this + 96);
    if ( !*((_QWORD *)this + 12) )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 96, a2, a3);
      v6 = CoCreateInstance(&CLSID_GroupPolicyObject, 0, 1u, &IID_IGroupPolicyObject2, v5);
      if ( v6 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2A,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\lockdownpolicytask.cpp",
          (const char *)(unsigned int)v6,
          ppv);
      v7 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)*v5 + 40LL))(*v5, 1);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2B,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\lockdownpolicytask.cpp",
          (const char *)(unsigned int)v7,
          ppv);
    }
    v8 = *v5;
    *a2 = *v5;
  }
  if ( v8 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 8LL))(v8);
  return a2;
}

```

## disassembly

```asm
0x1800233cc  push    rbx
0x1800233ce  push    rsi
0x1800233cf  push    rdi
0x1800233d0  push    r14
0x1800233d2  push    r15
0x1800233d4  sub     rsp, 40h
0x1800233d8  mov     rsi, rdx
0x1800233db  mov     r15, rcx
0x1800233de  test    r8d, r8d
0x1800233e1  jnz     loc_180023473
0x1800233e7  lea     rbx, [rcx+60h]
0x1800233eb  cmp     qword ptr [rbx], 0
0x1800233ef  jnz     short loc_180023468
0x1800233f1  mov     rcx, rbx
0x1800233f4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800233f9  mov     qword ptr [rsp+68h+ppv], rbx; int
0x1800233fe  lea     r9, IID_IGroupPolicyObject2; riid
0x180023405  xor     edx, edx; pUnkOuter
0x180023407  lea     r8d, [rdx+1]; dwClsContext
0x18002340b  lea     rcx, CLSID_GroupPolicyObject; rclsid
0x180023412  call    cs:__imp_CoCreateInstance
0x180023418  mov     rcx, [rsp+68h]; this
0x18002341d  test    eax, eax
0x18002341f  jns     short loc_180023436
0x180023421  mov     r9d, eax; char *
0x180023424  lea     r8, aPcshellShellRe_3; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002342b  mov     edx, 2Ah ; '*'; void *
0x180023430  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023436  mov     rcx, [rbx]
0x180023439  mov     rax, [rcx]
0x18002343c  mov     edx, 1
0x180023441  mov     rax, [rax+28h]
0x180023445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002344a  mov     rcx, [rsp+68h]; this
0x18002344f  test    eax, eax
0x180023451  jns     short loc_180023468
0x180023453  mov     r9d, eax; char *
0x180023456  lea     r8, aPcshellShellRe_3; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002345d  mov     edx, 2Bh ; '+'; void *
0x180023462  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023468  mov     rcx, [rbx]
0x18002346b  mov     [rsi], rcx
0x18002346e  jmp     loc_18002351D
0x180023473  cmp     r8d, 1
0x180023477  jnz     loc_180023531
0x18002347d  lea     r14, [rcx+68h]
0x180023481  cmp     qword ptr [r14], 0
0x180023485  jnz     loc_180023517
0x18002348b  mov     rcx, r14
0x18002348e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180023493  mov     qword ptr [rsp+68h+ppv], r14; int
0x180023498  lea     r9, IID_IGroupPolicyObject2; riid
0x18002349f  xor     edx, edx; pUnkOuter
0x1800234a1  lea     r8d, [rdx+1]; dwClsContext
0x1800234a5  lea     rcx, CLSID_GroupPolicyObject; rclsid
0x1800234ac  call    cs:__imp_CoCreateInstance
0x1800234b2  mov     rcx, [rsp+68h]; this
0x1800234b7  test    eax, eax
0x1800234b9  jns     short loc_1800234D0
0x1800234bb  mov     r9d, eax; char *
0x1800234be  lea     r8, aPcshellShellRe_3; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800234c5  mov     edx, 33h ; '3'; void *
0x1800234ca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800234d0  mov     rdi, [r14]
0x1800234d3  mov     rax, [rdi]
0x1800234d6  mov     rbx, [rax+0A8h]
0x1800234dd  mov     rcx, r15; this
0x1800234e0  call    ?GetUserSid@LockDownPolicyTask@@AEAAPEBGXZ; LockDownPolicyTask::GetUserSid(void)
0x1800234e5  mov     r8d, 1
0x1800234eb  mov     rdx, rax
0x1800234ee  mov     rcx, rdi
0x1800234f1  mov     rax, rbx
0x1800234f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234f9  mov     rcx, [rsp+68h]; this
0x1800234fe  test    eax, eax
0x180023500  jns     short loc_180023517
0x180023502  mov     r9d, eax; char *
0x180023505  lea     r8, aPcshellShellRe_3; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002350c  mov     edx, 34h ; '4'; void *
0x180023511  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023517  mov     rcx, [r14]
0x18002351a  mov     [rsi], rcx
0x18002351d  test    rcx, rcx
0x180023520  jz      short loc_18002352F
0x180023522  mov     rax, [rcx]
0x180023525  mov     rax, [rax+8]
0x180023529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002352e  nop
0x18002352f  jmp     short loc_180023538
0x180023531  mov     qword ptr [rdx], 0
0x180023538  mov     rax, rsi
0x18002353b  add     rsp, 40h
0x18002353f  pop     r15
0x180023541  pop     r14
0x180023543  pop     rdi
0x180023544  pop     rsi
0x180023545  pop     rbx
0x180023546  retn
```
