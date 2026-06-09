# LaunchAppAsUserTaskBase::GetRetailDemoAppsController(void)

- ea: `0x18001ee54`
- end: `0x18001eed6`
- name: `?GetRetailDemoAppsController@LaunchAppAsUserTaskBase@@IEAA?AV?$ComPtr@UIRetailDemoAppsController@@@WRL@Microsoft@@XZ`
- size: `130`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001eb10`
- `0x18001ebc0`
- `0x18001ec40`
- `0x18001f28c`
- `0x18001f5c4`

## callees

- `0x180008bbc`
- `0x18001094c`
- `0x18001ee54`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ee8c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ee8c`

## string_xrefs

- `0x18001ee9e`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LPVOID *__fastcall LaunchAppAsUserTaskBase::GetRetailDemoAppsController(__int64 a1, LPVOID *a2, __int64 a3)
{
  LPVOID *v4; // rdi
  HRESULT Instance; // eax
  LPVOID v6; // rcx
  int ppv; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = (LPVOID *)(a1 + 80);
  if ( !*(_QWORD *)(a1 + 80) )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 80, a2, a3);
    Instance = CoCreateInstance(
                 &GUID_1e46246f_b2ad_4a86_9e08_d0f9e01ee05d,
                 0,
                 1u,
                 &GUID_618f3f46_6b42_407a_9b32_690ac75e2e5e,
                 v4);
    if ( Instance < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE2,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
        (const char *)(unsigned int)Instance,
        ppv);
  }
  v6 = *v4;
  *a2 = *v4;
  if ( v6 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 8LL))(v6);
  return a2;
}

```

## disassembly

```asm
0x18001ee54  mov     [rsp+arg_0], rbx
0x18001ee59  push    rdi
0x18001ee5a  sub     rsp, 40h
0x18001ee5e  mov     rbx, rdx
0x18001ee61  lea     rdi, [rcx+50h]
0x18001ee65  cmp     qword ptr [rdi], 0
0x18001ee69  jnz     short loc_18001EEB0
0x18001ee6b  mov     rcx, rdi
0x18001ee6e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ee73  mov     qword ptr [rsp+48h+ppv], rdi; int
0x18001ee78  lea     r9, _GUID_618f3f46_6b42_407a_9b32_690ac75e2e5e; riid
0x18001ee7f  xor     edx, edx; pUnkOuter
0x18001ee81  lea     r8d, [rdx+1]; dwClsContext
0x18001ee85  lea     rcx, _GUID_1e46246f_b2ad_4a86_9e08_d0f9e01ee05d; rclsid
0x18001ee8c  call    cs:__imp_CoCreateInstance
0x18001ee92  mov     rcx, [rsp+48h]; this
0x18001ee97  test    eax, eax
0x18001ee99  jns     short loc_18001EEB0
0x18001ee9b  mov     r9d, eax; char *
0x18001ee9e  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001eea5  mov     edx, 0E2h; void *
0x18001eeaa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001eeb0  mov     rcx, [rdi]
0x18001eeb3  mov     [rbx], rcx
0x18001eeb6  test    rcx, rcx
0x18001eeb9  jz      short loc_18001EEC8
0x18001eebb  mov     rax, [rcx]
0x18001eebe  mov     rax, [rax+8]
0x18001eec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eec7  nop
0x18001eec8  mov     rax, rbx
0x18001eecb  mov     rbx, [rsp+48h+arg_0]
0x18001eed0  add     rsp, 40h
0x18001eed4  pop     rdi
0x18001eed5  retn
```
