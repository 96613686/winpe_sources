# ATL::CAtlExeModuleT<CTieringEngineService>::MonitorProc(void *)

- ea: `0x140003740`
- end: `0x1400037a8`
- name: `?MonitorProc@?$CAtlExeModuleT@VCTieringEngineService@@@ATL@@SAKPEAX@Z`
- size: `104`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003740`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSuspendClassObjects` at `0x140003777`
- `api-ms-win-core-com-l1-1-0!CoSuspendClassObjects` at `0x140003777`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003787`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003787`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140003750`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140003761`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140003750`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140003761`
- `USER32!PostThreadMessageW` at `0x14000379a`
- `USER32!PostThreadMessageW` at `0x14000379a`

## pseudocode

```c
__int64 __fastcall ATL::CAtlExeModuleT<CTieringEngineService>::MonitorProc(PVOID Parameter)
{
  DWORD v2; // edx
  void *v3; // rcx

  while ( 1 )
  {
    WaitForSingleObject(*((HANDLE *)Parameter + 10), 0xFFFFFFFF);
    do
    {
      v2 = *((_DWORD *)Parameter + 22);
      v3 = (void *)*((_QWORD *)Parameter + 10);
      *((_BYTE *)Parameter + 97) = 0;
    }
    while ( !WaitForSingleObject(v3, v2) );
    if ( !*((_BYTE *)Parameter + 97) && !*((_DWORD *)Parameter + 3) )
    {
      CoSuspendClassObjects();
      if ( !*((_DWORD *)Parameter + 3) )
        break;
    }
  }
  CloseHandle(*((HANDLE *)Parameter + 10));
  PostThreadMessageW(*((_DWORD *)Parameter + 18), 0x12u, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x140003740  push    rbx
0x140003742  sub     rsp, 20h
0x140003746  mov     rbx, rcx
0x140003749  mov     rcx, [rbx+50h]; hHandle
0x14000374d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140003750  call    cs:__imp_WaitForSingleObject
0x140003756  mov     edx, [rbx+58h]; dwMilliseconds
0x140003759  mov     rcx, [rbx+50h]; hHandle
0x14000375d  mov     byte ptr [rbx+61h], 0
0x140003761  call    cs:__imp_WaitForSingleObject
0x140003767  test    eax, eax
0x140003769  jz      short loc_140003756
0x14000376b  cmp     byte ptr [rbx+61h], 0
0x14000376f  jnz     short loc_140003749
0x140003771  cmp     dword ptr [rbx+0Ch], 0
0x140003775  jnz     short loc_140003749
0x140003777  call    cs:__imp_CoSuspendClassObjects
0x14000377d  cmp     dword ptr [rbx+0Ch], 0
0x140003781  jnz     short loc_140003749
0x140003783  mov     rcx, [rbx+50h]; hObject
0x140003787  call    cs:__imp_CloseHandle
0x14000378d  mov     ecx, [rbx+48h]; idThread
0x140003790  xor     r9d, r9d; lParam
0x140003793  xor     r8d, r8d; wParam
0x140003796  lea     edx, [r9+12h]; Msg
0x14000379a  call    cs:__imp_PostThreadMessageW
0x1400037a0  xor     eax, eax
0x1400037a2  add     rsp, 20h
0x1400037a6  pop     rbx
0x1400037a7  retn
```
