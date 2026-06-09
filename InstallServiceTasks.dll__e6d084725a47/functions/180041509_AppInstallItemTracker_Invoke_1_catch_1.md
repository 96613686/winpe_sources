# _AppInstallItemTracker::Invoke_::_1_::catch$1

- ea: `0x180041509`
- end: `0x1800415a4`
- name: `_AppInstallItemTracker::Invoke_::_1_::catch$1`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000f580`
- `0x18000fd08`
- `0x180012f10`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004153c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004153c`

## string_xrefs

- `0x18004151c`: `onecoreuap\enduser\winstore\installservice\lib\downloadandinstallpendingupdatesworker.cpp`
- `0x180041576`: `onecoreuap\enduser\winstore\installservice\lib\downloadandinstallpendingupdatesworker.cpp`
- `0x180041569`: `AppInstallItemTracker::Invoke`
- `0x180041559`: `Error Querying Status for ProductId: %s. Marking as Completed`

## pseudocode

```c
__int64 __fastcall AppInstallItemTracker::Invoke_::_1_::catch_1(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  int v5; // ebx
  __int64 v6; // rdi
  PCWSTR StringRawBuffer; // rax
  void *v8; // rdx

  v5 = wil::details::in1diag3::Log_CaughtException(
         *(wil::details::in1diag3 **)(a2 + 104),
         (void *)0xDB,
         (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\downloadandinstallpendingupdatesworker.cpp",
         a4);
  *(_DWORD *)(a2 + 120) = v5;
  v6 = *(_QWORD *)(a2 + 112);
  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(v6 + 88), 0);
  LogMessage(
    2u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\downloadandinstallpendingupdatesworker.cpp",
    0xDCu,
    "AppInstallItemTracker::Invoke",
    v5,
    L"Error Querying Status for ProductId: %s. Marking as Completed",
    0,
    0,
    StringRawBuffer);
  wil::details::SetEvent(*(wil::details **)(v6 + 96), v8);
  return 0;
}

```

## disassembly

```asm
0x180041509  mov     [rsp+arg_8], rdx
0x18004150e  push    rbx
0x18004150f  push    rbp
0x180041510  push    rdi
0x180041511  sub     rsp, 50h
0x180041515  mov     rbp, rdx
0x180041518  mov     rcx, [rbp+68h]; this
0x18004151c  lea     r8, aOnecoreuapEndu_10; "onecoreuap\\enduser\\winstore\\installs"...
0x180041523  mov     edx, 0DBh; void *
0x180041528  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18004152d  mov     ebx, eax
0x18004152f  mov     [rbp+78h], eax
0x180041532  xor     edx, edx; length
0x180041534  mov     rdi, [rbp+70h]
0x180041538  mov     rcx, [rdi+58h]; string
0x18004153c  call    cs:__imp_WindowsGetStringRawBuffer
0x180041542  mov     [rsp+68h+var_28], rax
0x180041547  mov     [rsp+68h+var_30], 0; unsigned __int16 *
0x180041550  mov     [rsp+68h+var_38], 0; char *
0x180041559  lea     rax, aErrorQueryingS; "Error Querying Status for ProductId: %s"...
0x180041560  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x180041565  mov     [rsp+68h+var_48], ebx; int
0x180041569  lea     r9, aAppinstallitem_0; "AppInstallItemTracker::Invoke"
0x180041570  mov     r8d, 0DCh; unsigned int
0x180041576  lea     rdx, aOnecoreuapEndu_10; "onecoreuap\\enduser\\winstore\\installs"...
0x18004157d  mov     ecx, 2; unsigned int
0x180041582  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180041587  mov     rcx, [rdi+60h]; this
0x18004158b  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180041590  nop
0x180041591  mov     rax, 0
0x18004159b  add     rsp, 50h
0x18004159f  pop     rdi
0x1800415a0  pop     rbp
0x1800415a1  pop     rbx
0x1800415a2  retn
```
