# ATL::CAtlExeModuleT<CRAServerModule>::Unlock(void)

- ea: `0x14000db90`
- end: `0x14000dbd3`
- name: `?Unlock@?$CAtlExeModuleT@VCRAServerModule@@@ATL@@UEAAJXZ`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000db90`

## import_xrefs

- `KERNEL32!SetEvent` at `0x14000dbb0`
- `KERNEL32!SetEvent` at `0x14000dbb0`
- `USER32!PostThreadMessageW` at `0x14000dbc5`
- `USER32!PostThreadMessageW` at `0x14000dbc5`

## pseudocode

```c
__int64 __fastcall ATL::CAtlExeModuleT<CRAServerModule>::Unlock(__int64 a1)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 12));
  if ( !v1 )
  {
    if ( *(_BYTE *)(a1 + 96) )
    {
      *(_BYTE *)(a1 + 97) = 1;
      SetEvent(*(HANDLE *)(a1 + 80));
    }
    else
    {
      PostThreadMessageW(*(_DWORD *)(a1 + 72), 0x12u, 0, 0);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x14000db90  push    rbx
0x14000db92  sub     rsp, 20h
0x14000db96  or      ebx, 0FFFFFFFFh
0x14000db99  lock xadd [rcx+0Ch], ebx
0x14000db9e  sub     ebx, 1
0x14000dba1  jnz     short loc_14000DBCB
0x14000dba3  cmp     [rcx+60h], bl
0x14000dba6  jz      short loc_14000DBB8
0x14000dba8  mov     byte ptr [rcx+61h], 1
0x14000dbac  mov     rcx, [rcx+50h]; hEvent
0x14000dbb0  call    cs:__imp_SetEvent
0x14000dbb6  jmp     short loc_14000DBCB
0x14000dbb8  mov     ecx, [rcx+48h]; idThread
0x14000dbbb  xor     r9d, r9d; lParam
0x14000dbbe  xor     r8d, r8d; wParam
0x14000dbc1  lea     edx, [r9+12h]; Msg
0x14000dbc5  call    cs:__imp_PostThreadMessageW
0x14000dbcb  mov     eax, ebx
0x14000dbcd  add     rsp, 20h
0x14000dbd1  pop     rbx
0x14000dbd2  retn
```
