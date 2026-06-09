# SystemSettings::WorkAccess::MDMAADTokenRepair::Invoke(HWND__ *)

- ea: `0x180026860`
- end: `0x1800268cf`
- name: `?Invoke@MDMAADTokenRepair@WorkAccess@SystemSettings@@UEAAJPEAUHWND__@@@Z`
- size: `111`
- prototype: `__int64 __fastcall(PVOID pv, HWND)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800096ec`
- `0x180026860`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800268ba`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800268ba`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002687d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002687d`

## string_xrefs

- `0x18002689a`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::MDMAADTokenRepair::Invoke(_QWORD *pv, HWND a2)
{
  struct _TP_WORK *ThreadpoolWork; // rax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  pv[29] = a2;
  ThreadpoolWork = CreateThreadpoolWork(SystemSettings::WorkAccess::MDMAADTokenRepair::s_AADTokenRepairWorker, pv, 0);
  pv[27] = ThreadpoolWork;
  if ( ThreadpoolWork )
  {
    SubmitThreadpoolWork(ThreadpoolWork);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A8,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
      (const char *)0x80004005LL,
      v5);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180026860  push    rbx; int
0x180026862  sub     rsp, 20h
0x180026866  mov     [rcx+0E8h], rdx
0x18002686d  mov     rbx, rcx
0x180026870  mov     rdx, rcx; pv
0x180026873  xor     r8d, r8d; pcbe
0x180026876  lea     rcx, ?s_AADTokenRepairWorker@MDMAADTokenRepair@WorkAccess@SystemSettings@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18002687d  call    cs:__imp_CreateThreadpoolWork
0x180026884  nop     dword ptr [rax+rax+00h]
0x180026889  mov     [rbx+0D8h], rax
0x180026890  test    rax, rax
0x180026893  jnz     short loc_1800268B7
0x180026895  mov     rcx, [rsp+28h]; this
0x18002689a  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x1800268a1  mov     ebx, 80004005h
0x1800268a6  mov     edx, 2A8h; void *
0x1800268ab  mov     r9d, ebx; char *
0x1800268ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800268b3  mov     eax, ebx
0x1800268b5  jmp     short loc_1800268C8
0x1800268b7  mov     rcx, rax; pwk
0x1800268ba  call    cs:__imp_SubmitThreadpoolWork
0x1800268c1  nop     dword ptr [rax+rax+00h]
0x1800268c6  xor     eax, eax
0x1800268c8  add     rsp, 20h
0x1800268cc  pop     rbx
0x1800268cd  retn
```
