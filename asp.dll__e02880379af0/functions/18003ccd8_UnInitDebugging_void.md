# UnInitDebugging(void)

- ea: `0x18003ccd8`
- end: `0x18003ce33`
- name: `?UnInitDebugging@@YAJXZ`
- size: `347`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003f760`

## callees

- `0x18000f614`
- `0x18003ccd8`
- `0x180064010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18003ce20`
- `KERNEL32!CloseHandle` at `0x18003ce20`
- `KERNEL32!SetEvent` at `0x18003cdfc`
- `KERNEL32!SetEvent` at `0x18003cdfc`
- `KERNEL32!Sleep` at `0x18003ce09`
- `KERNEL32!Sleep` at `0x18003ce09`
- `KERNEL32!DeleteCriticalSection` at `0x18003cd50`
- `KERNEL32!DeleteCriticalSection` at `0x18003cd50`

## pseudocode

```c
__int64 UnInitDebugging(void)
{
  __int64 v0; // rdi
  __int64 v1; // rbx

  v0 = qword_180078010;
  if ( qword_180078010 )
  {
    do
    {
      v1 = *(_QWORD *)(v0 + 32);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v0 + 40) + 88LL))(*(_QWORD *)(v0 + 40));
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v0 + 40) + 72LL))(*(_QWORD *)(v0 + 40));
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v0 + 40) + 16LL))(*(_QWORD *)(v0 + 40));
      (**(void (__fastcall ***)(__int64, __int64))v0)(v0, 1);
      v0 = v1;
    }
    while ( v1 );
  }
  CHashTable::UnInit((CHashTable *)&off_180078000);
  DeleteCriticalSection(&stru_18007E430);
  if ( g_pDebugAppRoot )
  {
    ((void (__fastcall *)(struct IDebugApplicationNode *))g_pDebugAppRoot->lpVtbl->Detach)(g_pDebugAppRoot);
    ((void (__fastcall *)(struct IDebugApplicationNode *))g_pDebugAppRoot->lpVtbl->Close)(g_pDebugAppRoot);
    ((void (__fastcall *)(struct IDebugApplicationNode *))g_pDebugAppRoot->lpVtbl->Release)(g_pDebugAppRoot);
  }
  if ( g_pDebugApp )
  {
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)g_pPDM + 48LL))(g_pPDM, (unsigned int)dword_18007E428);
    ((void (__fastcall *)(struct IDebugApplication64 *))g_pDebugApp->lpVtbl->Close)(g_pDebugApp);
    ((void (__fastcall *)(struct IDebugApplication64 *))g_pDebugApp->lpVtbl->Release)(g_pDebugApp);
    g_pDebugApp = 0;
  }
  if ( g_pPDM )
  {
    SetEvent(hObject);
    while ( g_pPDM )
      Sleep(0x64u);
    CloseHandle(hObject);
  }
  return 0;
}

```

## disassembly

```asm
0x18003ccd8  mov     [rsp+arg_0], rbx
0x18003ccdd  push    rdi
0x18003ccde  sub     rsp, 20h
0x18003cce2  mov     rdi, cs:qword_180078010
0x18003cce9  test    rdi, rdi
0x18003ccec  jz      short loc_18003CD3D
0x18003ccee  mov     rcx, [rdi+28h]
0x18003ccf2  mov     rbx, [rdi+20h]
0x18003ccf6  mov     rax, [rcx]
0x18003ccf9  mov     rax, [rax+58h]
0x18003ccfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd02  mov     rcx, [rdi+28h]
0x18003cd06  mov     rax, [rcx]
0x18003cd09  mov     rax, [rax+48h]
0x18003cd0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd12  mov     rcx, [rdi+28h]
0x18003cd16  mov     rax, [rcx]
0x18003cd19  mov     rax, [rax+10h]
0x18003cd1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd22  mov     rax, [rdi]
0x18003cd25  mov     edx, 1
0x18003cd2a  mov     rcx, rdi
0x18003cd2d  mov     rax, [rax]
0x18003cd30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd35  mov     rdi, rbx
0x18003cd38  test    rbx, rbx
0x18003cd3b  jnz     short loc_18003CCEE
0x18003cd3d  lea     rcx, off_180078000; this
0x18003cd44  call    ?UnInit@CHashTable@@QEAAJXZ; CHashTable::UnInit(void)
0x18003cd49  lea     rcx, stru_18007E430; lpCriticalSection
0x18003cd50  call    cs:__imp_DeleteCriticalSection
0x18003cd56  mov     rcx, cs:?g_pDebugAppRoot@@3PEAUIDebugApplicationNode@@EA; IDebugApplicationNode * g_pDebugAppRoot
0x18003cd5d  test    rcx, rcx
0x18003cd60  jz      short loc_18003CD94
0x18003cd62  mov     rax, [rcx]
0x18003cd65  mov     rax, [rax+58h]
0x18003cd69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd6e  mov     rcx, cs:?g_pDebugAppRoot@@3PEAUIDebugApplicationNode@@EA; IDebugApplicationNode * g_pDebugAppRoot
0x18003cd75  mov     rax, [rcx]
0x18003cd78  mov     rax, [rax+48h]
0x18003cd7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd81  mov     rcx, cs:?g_pDebugAppRoot@@3PEAUIDebugApplicationNode@@EA; IDebugApplicationNode * g_pDebugAppRoot
0x18003cd88  mov     rax, [rcx]
0x18003cd8b  mov     rax, [rax+10h]
0x18003cd8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd94  cmp     cs:?g_pDebugApp@@3PEAUIDebugApplication64@@EA, 0; IDebugApplication64 * g_pDebugApp
0x18003cd9c  jz      short loc_18003CDEB
0x18003cd9e  mov     rcx, cs:?g_pPDM@@3PEAUIProcessDebugManager64@@EA; IProcessDebugManager64 * g_pPDM
0x18003cda5  mov     edx, cs:dword_18007E428
0x18003cdab  mov     rax, [rcx]
0x18003cdae  mov     rax, [rax+30h]
0x18003cdb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cdb7  mov     rcx, cs:?g_pDebugApp@@3PEAUIDebugApplication64@@EA; IDebugApplication64 * g_pDebugApp
0x18003cdbe  mov     rax, [rcx]
0x18003cdc1  mov     rax, [rax+98h]
0x18003cdc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cdcd  mov     rcx, cs:?g_pDebugApp@@3PEAUIDebugApplication64@@EA; IDebugApplication64 * g_pDebugApp
0x18003cdd4  mov     rax, [rcx]
0x18003cdd7  mov     rax, [rax+10h]
0x18003cddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cde0  mov     cs:?g_pDebugApp@@3PEAUIDebugApplication64@@EA, 0; IDebugApplication64 * g_pDebugApp
0x18003cdeb  cmp     cs:?g_pPDM@@3PEAUIProcessDebugManager64@@EA, 0; IProcessDebugManager64 * g_pPDM
0x18003cdf3  jz      short loc_18003CE26
0x18003cdf5  mov     rcx, cs:hObject; hEvent
0x18003cdfc  call    cs:__imp_SetEvent
0x18003ce02  jmp     short loc_18003CE0F
0x18003ce04  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18003ce09  call    cs:__imp_Sleep
0x18003ce0f  cmp     cs:?g_pPDM@@3PEAUIProcessDebugManager64@@EA, 0; IProcessDebugManager64 * g_pPDM
0x18003ce17  jnz     short loc_18003CE04
0x18003ce19  mov     rcx, cs:hObject; hObject
0x18003ce20  call    cs:__imp_CloseHandle
0x18003ce26  mov     rbx, [rsp+28h+arg_0]
0x18003ce2b  xor     eax, eax
0x18003ce2d  add     rsp, 20h
0x18003ce31  pop     rdi
0x18003ce32  retn
```
