# Windows::Globalization::Spelling::CHostModule::TimeoutMonitorProc(void *)

- ea: `0x140005d00`
- end: `0x140005d7e`
- name: `?TimeoutMonitorProc@CHostModule@Spelling@Globalization@Windows@@SAKPEAX@Z`
- size: `126`
- prototype: `__int64 __fastcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140005d00`
- `0x140013010`

## import_xrefs

- `USER32!PostThreadMessageW` at `0x140005d70`
- `USER32!PostThreadMessageW` at `0x140005d70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005d5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005d5a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140005d13`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140005d2d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140005d13`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140005d2d`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::CHostModule::TimeoutMonitorProc(LPVOID lpThreadParameter)
{
  DWORD v2; // edx
  void *v3; // rcx

  do
  {
    WaitForSingleObject(*((HANDLE *)lpThreadParameter + 17), 0xFFFFFFFF);
    do
    {
      v2 = *((_DWORD *)lpThreadParameter + 38);
      v3 = (void *)*((_QWORD *)lpThreadParameter + 17);
      *((_BYTE *)lpThreadParameter + 160) = 0;
    }
    while ( !WaitForSingleObject(v3, v2) );
  }
  while ( *((_BYTE *)lpThreadParameter + 160)
       || (*(unsigned int (__fastcall **)(LPVOID))(*(_QWORD *)lpThreadParameter + 24LL))(lpThreadParameter) );
  CloseHandle(*((HANDLE *)lpThreadParameter + 17));
  PostThreadMessageW(*((_DWORD *)lpThreadParameter + 32), 0x12u, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x140005d00  push    rbx
0x140005d02  sub     rsp, 20h
0x140005d06  mov     rbx, rcx
0x140005d09  mov     rcx, [rbx+88h]; hHandle
0x140005d10  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140005d13  call    cs:__imp_WaitForSingleObject
0x140005d19  mov     edx, [rbx+98h]; dwMilliseconds
0x140005d1f  mov     rcx, [rbx+88h]; hHandle
0x140005d26  mov     byte ptr [rbx+0A0h], 0
0x140005d2d  call    cs:__imp_WaitForSingleObject
0x140005d33  test    eax, eax
0x140005d35  jz      short loc_140005D19
0x140005d37  cmp     byte ptr [rbx+0A0h], 0
0x140005d3e  jnz     short loc_140005D09
0x140005d40  mov     rax, [rbx]
0x140005d43  mov     rcx, rbx
0x140005d46  mov     rax, [rax+18h]
0x140005d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d4f  test    eax, eax
0x140005d51  jnz     short loc_140005D09
0x140005d53  mov     rcx, [rbx+88h]; hObject
0x140005d5a  call    cs:__imp_CloseHandle
0x140005d60  mov     ecx, [rbx+80h]; idThread
0x140005d66  xor     r9d, r9d; lParam
0x140005d69  xor     r8d, r8d; wParam
0x140005d6c  lea     edx, [r9+12h]; Msg
0x140005d70  call    cs:__imp_PostThreadMessageW
0x140005d76  xor     eax, eax
0x140005d78  add     rsp, 20h
0x140005d7c  pop     rbx
0x140005d7d  retn
```
