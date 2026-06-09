# RemoteAppUtil::InstallRemoteApp(_SwJob)

- ea: `0x180019f78`
- end: `0x18001a02c`
- name: `?InstallRemoteApp@RemoteAppUtil@@SAJU_SwJob@@@Z`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180010eac`

## callees

- `0x1800065f8`
- `0x1800070e4`
- `0x180007498`
- `0x18000bd00`
- `0x180019a88`
- `0x180019b24`
- `0x180019f78`
- `0x18001f420`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RemoteAppUtil::InstallRemoteApp(__int64 a1)
{
  __int64 v2; // rax
  _QWORD *v3; // rdx
  int ThreadAndDispatchAction; // edi
  _BYTE Parameter[32]; // [rsp+30h] [rbp-88h] BYREF
  _BYTE v7[80]; // [rsp+50h] [rbp-68h] BYREF

  RemoteAppDispatchParam::RemoteAppDispatchParam((RemoteAppDispatchParam *)Parameter);
  v2 = *(_QWORD *)(a1 + 80);
  v3 = (_QWORD *)(*(_QWORD *)v2 + 16LL);
  if ( *(_QWORD *)(*(_QWORD *)v2 + 40LL) >= 8u )
    v3 = (_QWORD *)*v3;
  std::wstring::assign(v7, v3);
  std::wstring::operator=(Parameter, a1 + 32);
  ThreadAndDispatchAction = CreateThreadAndDispatchAction(
                              (LPTHREAD_START_ROUTINE)RemoteAppUtil::InstallRemoteApp,
                              Parameter);
  if ( ThreadAndDispatchAction < 0 )
    *(_DWORD *)(a1 + 96) = 120;
  RemoteAppDispatchParam::~RemoteAppDispatchParam((RemoteAppDispatchParam *)Parameter);
  _SwJob::~_SwJob((_SwJob *)a1);
  return (unsigned int)ThreadAndDispatchAction;
}

```

## disassembly

```asm
0x180019f78  mov     [rsp+arg_8], rbx
0x180019f7d  push    rdi
0x180019f7e  sub     rsp, 0B0h
0x180019f85  mov     rax, cs:__security_cookie
0x180019f8c  xor     rax, rsp
0x180019f8f  mov     [rsp+0B8h+var_18], rax
0x180019f97  mov     rbx, rcx
0x180019f9a  mov     [rsp+0B8h+var_98], rcx
0x180019f9f  lea     rcx, [rsp+0B8h+Parameter]; this
0x180019fa4  call    ??0RemoteAppDispatchParam@@QEAA@XZ; RemoteAppDispatchParam::RemoteAppDispatchParam(void)
0x180019fa9  nop
0x180019faa  mov     rax, [rbx+50h]
0x180019fae  mov     rdx, [rax]
0x180019fb1  add     rdx, 10h
0x180019fb5  cmp     qword ptr [rdx+18h], 8
0x180019fba  jb      short loc_180019FBF
0x180019fbc  mov     rdx, [rdx]
0x180019fbf  lea     rcx, [rsp+0B8h+var_68]
0x180019fc4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180019fc9  lea     rdx, [rbx+20h]
0x180019fcd  lea     rcx, [rsp+0B8h+Parameter]
0x180019fd2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180019fd7  lea     rdx, [rsp+0B8h+Parameter]; lpParameter
0x180019fdc  lea     rcx, ?InstallRemoteApp@RemoteAppUtil@@SAKPEAX@Z; lpStartAddress
0x180019fe3  call    ?CreateThreadAndDispatchAction@@YAJP6AKPEAX@Z0@Z; CreateThreadAndDispatchAction(ulong (*)(void *),void *)
0x180019fe8  mov     edi, eax
0x180019fea  test    eax, eax
0x180019fec  jns     short loc_180019FF5
0x180019fee  mov     dword ptr [rbx+60h], 78h ; 'x'
0x180019ff5  lea     rcx, [rsp+0B8h+Parameter]; this
0x180019ffa  call    ??1RemoteAppDispatchParam@@QEAA@XZ; RemoteAppDispatchParam::~RemoteAppDispatchParam(void)
0x180019fff  nop
0x18001a000  mov     rcx, rbx; this
0x18001a003  call    ??1_SwJob@@QEAA@XZ; _SwJob::~_SwJob(void)
0x18001a008  mov     eax, edi
0x18001a00a  mov     rcx, [rsp+0B8h+var_18]
0x18001a012  xor     rcx, rsp; StackCookie
0x18001a015  call    __security_check_cookie
0x18001a01a  mov     rbx, [rsp+0B8h+arg_8]
0x18001a022  add     rsp, 0B0h
0x18001a029  pop     rdi
0x18001a02a  retn
```
