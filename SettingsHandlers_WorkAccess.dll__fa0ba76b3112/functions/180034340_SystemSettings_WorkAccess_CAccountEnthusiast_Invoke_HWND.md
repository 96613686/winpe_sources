# SystemSettings::WorkAccess::CAccountEnthusiast::Invoke(HWND__ *)

- ea: `0x180034340`
- end: `0x1800343af`
- name: `?Invoke@CAccountEnthusiast@WorkAccess@SystemSettings@@UEAAJPEAUHWND__@@@Z`
- size: `111`
- prototype: `__int64 __fastcall(PVOID pv, HWND)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800096ec`
- `0x180034340`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003439a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003439a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18003435d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18003435d`

## string_xrefs

- `0x18003437a`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::CAccountEnthusiast::Invoke(_QWORD *pv, HWND a2)
{
  struct _TP_WORK *ThreadpoolWork; // rax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  pv[38] = a2;
  ThreadpoolWork = CreateThreadpoolWork(SystemSettings::WorkAccess::CAccountEnthusiast::s_DeviceManagementWorker, pv, 0);
  pv[37] = ThreadpoolWork;
  if ( ThreadpoolWork )
  {
    SubmitThreadpoolWork(ThreadpoolWork);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x342,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
      (const char *)0x80004005LL,
      v5);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180034340  push    rbx; int
0x180034342  sub     rsp, 20h
0x180034346  mov     [rcx+130h], rdx
0x18003434d  mov     rbx, rcx
0x180034350  mov     rdx, rcx; pv
0x180034353  xor     r8d, r8d; pcbe
0x180034356  lea     rcx, ?s_DeviceManagementWorker@CAccountEnthusiast@WorkAccess@SystemSettings@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18003435d  call    cs:__imp_CreateThreadpoolWork
0x180034364  nop     dword ptr [rax+rax+00h]
0x180034369  mov     [rbx+128h], rax
0x180034370  test    rax, rax
0x180034373  jnz     short loc_180034397
0x180034375  mov     rcx, [rsp+28h]; this
0x18003437a  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180034381  mov     ebx, 80004005h
0x180034386  mov     edx, 342h; void *
0x18003438b  mov     r9d, ebx; char *
0x18003438e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034393  mov     eax, ebx
0x180034395  jmp     short loc_1800343A8
0x180034397  mov     rcx, rax; pwk
0x18003439a  call    cs:__imp_SubmitThreadpoolWork
0x1800343a1  nop     dword ptr [rax+rax+00h]
0x1800343a6  xor     eax, eax
0x1800343a8  add     rsp, 20h
0x1800343ac  pop     rbx
0x1800343ad  retn
```
