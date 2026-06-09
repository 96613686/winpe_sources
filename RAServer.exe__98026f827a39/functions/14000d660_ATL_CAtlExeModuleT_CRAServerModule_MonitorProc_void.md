# ATL::CAtlExeModuleT<CRAServerModule>::MonitorProc(void *)

- ea: `0x14000d660`
- end: `0x14000d6c8`
- name: `?MonitorProc@?$CAtlExeModuleT@VCRAServerModule@@@ATL@@SAKPEAX@Z`
- size: `104`
- prototype: `__int64 __fastcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000d660`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x14000d670`
- `KERNEL32!WaitForSingleObject` at `0x14000d681`
- `KERNEL32!WaitForSingleObject` at `0x14000d670`
- `KERNEL32!WaitForSingleObject` at `0x14000d681`
- `KERNEL32!CloseHandle` at `0x14000d6a7`
- `KERNEL32!CloseHandle` at `0x14000d6a7`
- `USER32!PostThreadMessageW` at `0x14000d6ba`
- `USER32!PostThreadMessageW` at `0x14000d6ba`
- `api-ms-win-core-com-l1-1-0!CoSuspendClassObjects` at `0x14000d697`
- `api-ms-win-core-com-l1-1-0!CoSuspendClassObjects` at `0x14000d697`

## pseudocode

```c
__int64 __fastcall ATL::CAtlExeModuleT<CRAServerModule>::MonitorProc(LPVOID lpThreadParameter)
{
  DWORD v2; // edx
  void *v3; // rcx

  while ( 1 )
  {
    WaitForSingleObject(*((HANDLE *)lpThreadParameter + 10), 0xFFFFFFFF);
    do
    {
      v2 = *((_DWORD *)lpThreadParameter + 22);
      v3 = (void *)*((_QWORD *)lpThreadParameter + 10);
      *((_BYTE *)lpThreadParameter + 97) = 0;
    }
    while ( !WaitForSingleObject(v3, v2) );
    if ( !*((_BYTE *)lpThreadParameter + 97) && !*((_DWORD *)lpThreadParameter + 3) )
    {
      CoSuspendClassObjects();
      if ( !*((_DWORD *)lpThreadParameter + 3) )
        break;
    }
  }
  CloseHandle(*((HANDLE *)lpThreadParameter + 10));
  PostThreadMessageW(*((_DWORD *)lpThreadParameter + 18), 0x12u, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x14000d660  push    rbx
0x14000d662  sub     rsp, 20h
0x14000d666  mov     rbx, rcx
0x14000d669  mov     rcx, [rbx+50h]; hHandle
0x14000d66d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000d670  call    cs:__imp_WaitForSingleObject
0x14000d676  mov     edx, [rbx+58h]; dwMilliseconds
0x14000d679  mov     rcx, [rbx+50h]; hHandle
0x14000d67d  mov     byte ptr [rbx+61h], 0
0x14000d681  call    cs:__imp_WaitForSingleObject
0x14000d687  test    eax, eax
0x14000d689  jz      short loc_14000D676
0x14000d68b  cmp     byte ptr [rbx+61h], 0
0x14000d68f  jnz     short loc_14000D669
0x14000d691  cmp     dword ptr [rbx+0Ch], 0
0x14000d695  jnz     short loc_14000D669
0x14000d697  call    cs:__imp_CoSuspendClassObjects
0x14000d69d  cmp     dword ptr [rbx+0Ch], 0
0x14000d6a1  jnz     short loc_14000D669
0x14000d6a3  mov     rcx, [rbx+50h]; hObject
0x14000d6a7  call    cs:__imp_CloseHandle
0x14000d6ad  mov     ecx, [rbx+48h]; idThread
0x14000d6b0  xor     r9d, r9d; lParam
0x14000d6b3  xor     r8d, r8d; wParam
0x14000d6b6  lea     edx, [r9+12h]; Msg
0x14000d6ba  call    cs:__imp_PostThreadMessageW
0x14000d6c0  xor     eax, eax
0x14000d6c2  add     rsp, 20h
0x14000d6c6  pop     rbx
0x14000d6c7  retn
```
