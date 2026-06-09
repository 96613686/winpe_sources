# ATL::CAtlExeModuleT<Windows::Globalization::Spelling::CHostModule>::MonitorProc(void *)

- ea: `0x140004000`
- end: `0x140004068`
- name: `?MonitorProc@?$CAtlExeModuleT@VCHostModule@Spelling@Globalization@Windows@@@ATL@@SAKPEAX@Z`
- size: `104`
- prototype: `__int64 __fastcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140004000`

## import_xrefs

- `USER32!PostThreadMessageW` at `0x14000405a`
- `USER32!PostThreadMessageW` at `0x14000405a`
- `api-ms-win-core-com-l1-1-0!CoSuspendClassObjects` at `0x140004037`
- `api-ms-win-core-com-l1-1-0!CoSuspendClassObjects` at `0x140004037`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004047`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004047`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004010`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004021`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004010`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004021`

## pseudocode

```c
__int64 __fastcall ATL::CAtlExeModuleT<Windows::Globalization::Spelling::CHostModule>::MonitorProc(
        LPVOID lpThreadParameter)
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
0x140004000  push    rbx
0x140004002  sub     rsp, 20h
0x140004006  mov     rbx, rcx
0x140004009  mov     rcx, [rbx+50h]; hHandle
0x14000400d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140004010  call    cs:__imp_WaitForSingleObject
0x140004016  mov     edx, [rbx+58h]; dwMilliseconds
0x140004019  mov     rcx, [rbx+50h]; hHandle
0x14000401d  mov     byte ptr [rbx+61h], 0
0x140004021  call    cs:__imp_WaitForSingleObject
0x140004027  test    eax, eax
0x140004029  jz      short loc_140004016
0x14000402b  cmp     byte ptr [rbx+61h], 0
0x14000402f  jnz     short loc_140004009
0x140004031  cmp     dword ptr [rbx+0Ch], 0
0x140004035  jnz     short loc_140004009
0x140004037  call    cs:__imp_CoSuspendClassObjects
0x14000403d  cmp     dword ptr [rbx+0Ch], 0
0x140004041  jnz     short loc_140004009
0x140004043  mov     rcx, [rbx+50h]; hObject
0x140004047  call    cs:__imp_CloseHandle
0x14000404d  mov     ecx, [rbx+48h]; idThread
0x140004050  xor     r9d, r9d; lParam
0x140004053  xor     r8d, r8d; wParam
0x140004056  lea     edx, [r9+12h]; Msg
0x14000405a  call    cs:__imp_PostThreadMessageW
0x140004060  xor     eax, eax
0x140004062  add     rsp, 20h
0x140004066  pop     rbx
0x140004067  retn
```
