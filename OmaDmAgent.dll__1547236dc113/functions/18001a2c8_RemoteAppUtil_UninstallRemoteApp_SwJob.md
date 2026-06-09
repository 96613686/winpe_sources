# RemoteAppUtil::UninstallRemoteApp(_SwJob)

- ea: `0x18001a2c8`
- end: `0x18001a371`
- name: `?UninstallRemoteApp@RemoteAppUtil@@SAJU_SwJob@@@Z`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18000dcb4`

## callees

- `0x1800065f8`
- `0x1800070e4`
- `0x180007498`
- `0x18000bd00`
- `0x180019a88`
- `0x180019b24`
- `0x18001a2c8`
- `0x18001f420`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RemoteAppUtil::UninstallRemoteApp(_SwJob *a1)
{
  __int64 v2; // rax
  _QWORD *v3; // rdx
  unsigned int ThreadAndDispatchAction; // ebx
  _BYTE Parameter[32]; // [rsp+30h] [rbp-88h] BYREF
  _BYTE v7[80]; // [rsp+50h] [rbp-68h] BYREF

  RemoteAppDispatchParam::RemoteAppDispatchParam((RemoteAppDispatchParam *)Parameter);
  v2 = *((_QWORD *)a1 + 10);
  v3 = (_QWORD *)(*(_QWORD *)v2 + 16LL);
  if ( *(_QWORD *)(*(_QWORD *)v2 + 40LL) >= 8u )
    v3 = (_QWORD *)*v3;
  std::wstring::assign(v7, v3);
  std::wstring::operator=(Parameter, (char *)a1 + 32);
  ThreadAndDispatchAction = CreateThreadAndDispatchAction(
                              (LPTHREAD_START_ROUTINE)RemoteAppUtil::UninstallRemoteApp,
                              Parameter);
  RemoteAppDispatchParam::~RemoteAppDispatchParam((RemoteAppDispatchParam *)Parameter);
  _SwJob::~_SwJob(a1);
  return ThreadAndDispatchAction;
}

```

## disassembly

```asm
0x18001a2c8  mov     [rsp+arg_8], rbx
0x18001a2cd  push    rdi
0x18001a2ce  sub     rsp, 0B0h
0x18001a2d5  mov     rax, cs:__security_cookie
0x18001a2dc  xor     rax, rsp
0x18001a2df  mov     [rsp+0B8h+var_18], rax
0x18001a2e7  mov     rdi, rcx
0x18001a2ea  mov     [rsp+0B8h+var_98], rcx
0x18001a2ef  lea     rcx, [rsp+0B8h+Parameter]; this
0x18001a2f4  call    ??0RemoteAppDispatchParam@@QEAA@XZ; RemoteAppDispatchParam::RemoteAppDispatchParam(void)
0x18001a2f9  nop
0x18001a2fa  mov     rax, [rdi+50h]
0x18001a2fe  mov     rdx, [rax]
0x18001a301  add     rdx, 10h
0x18001a305  cmp     qword ptr [rdx+18h], 8
0x18001a30a  jb      short loc_18001A30F
0x18001a30c  mov     rdx, [rdx]
0x18001a30f  lea     rcx, [rsp+0B8h+var_68]
0x18001a314  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001a319  lea     rdx, [rdi+20h]
0x18001a31d  lea     rcx, [rsp+0B8h+Parameter]
0x18001a322  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001a327  lea     rdx, [rsp+0B8h+Parameter]; lpParameter
0x18001a32c  lea     rcx, ?UninstallRemoteApp@RemoteAppUtil@@SAKPEAX@Z; lpStartAddress
0x18001a333  call    ?CreateThreadAndDispatchAction@@YAJP6AKPEAX@Z0@Z; CreateThreadAndDispatchAction(ulong (*)(void *),void *)
0x18001a338  mov     ebx, eax
0x18001a33a  lea     rcx, [rsp+0B8h+Parameter]; this
0x18001a33f  call    ??1RemoteAppDispatchParam@@QEAA@XZ; RemoteAppDispatchParam::~RemoteAppDispatchParam(void)
0x18001a344  nop
0x18001a345  mov     rcx, rdi; this
0x18001a348  call    ??1_SwJob@@QEAA@XZ; _SwJob::~_SwJob(void)
0x18001a34d  mov     eax, ebx
0x18001a34f  mov     rcx, [rsp+0B8h+var_18]
0x18001a357  xor     rcx, rsp; StackCookie
0x18001a35a  call    __security_check_cookie
0x18001a35f  mov     rbx, [rsp+0B8h+arg_8]
0x18001a367  add     rsp, 0B0h
0x18001a36e  pop     rdi
0x18001a36f  retn
```
