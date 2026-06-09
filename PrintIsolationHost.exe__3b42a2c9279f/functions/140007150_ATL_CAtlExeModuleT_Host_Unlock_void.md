# ATL::CAtlExeModuleT<Host>::Unlock(void)

- ea: `0x140007150`
- end: `0x140007193`
- name: `?Unlock@?$CAtlExeModuleT@VHost@@@ATL@@UEAAJXZ`
- size: `67`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140007150`

## import_xrefs

- `KERNEL32!SetEvent` at `0x140007170`
- `KERNEL32!SetEvent` at `0x140007170`
- `USER32!PostThreadMessageW` at `0x140007185`
- `USER32!PostThreadMessageW` at `0x140007185`

## pseudocode

```c
__int64 __fastcall ATL::CAtlExeModuleT<Host>::Unlock(__int64 a1)
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
0x140007150  push    rbx
0x140007152  sub     rsp, 20h
0x140007156  or      ebx, 0FFFFFFFFh
0x140007159  lock xadd [rcx+0Ch], ebx
0x14000715e  sub     ebx, 1
0x140007161  jnz     short loc_14000718B
0x140007163  cmp     [rcx+60h], bl
0x140007166  jz      short loc_140007178
0x140007168  mov     byte ptr [rcx+61h], 1
0x14000716c  mov     rcx, [rcx+50h]; hEvent
0x140007170  call    cs:__imp_SetEvent
0x140007176  jmp     short loc_14000718B
0x140007178  mov     ecx, [rcx+48h]; idThread
0x14000717b  xor     r9d, r9d; lParam
0x14000717e  xor     r8d, r8d; wParam
0x140007181  lea     edx, [r9+12h]; Msg
0x140007185  call    cs:__imp_PostThreadMessageW
0x14000718b  mov     eax, ebx
0x14000718d  add     rsp, 20h
0x140007191  pop     rbx
0x140007192  retn
```
