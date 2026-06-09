# CPimcManager::HookThreadProc(void *)

- ea: `0x18000ad10`
- end: `0x18000ada5`
- name: `?HookThreadProc@CPimcManager@@SAKPEAX@Z`
- size: `149`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000ad10`
- `0x18000b6b8`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000ad1d`
- `KERNEL32!SetEvent` at `0x18000ad74`
- `KERNEL32!SetEvent` at `0x18000ad1d`
- `KERNEL32!SetEvent` at `0x18000ad74`
- `USER32!PeekMessageW` at `0x18000ad94`
- `USER32!PeekMessageW` at `0x18000ad94`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x18000ad55`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x18000ad55`

## pseudocode

```c
__int64 __fastcall CPimcManager::HookThreadProc(HANDLE *Parameter)
{
  DWORD v2; // eax
  DWORD v3; // eax
  DWORD v4; // eax
  HANDLE pHandles[2]; // [rsp+30h] [rbp-48h] BYREF
  tagMSG Msg; // [rsp+40h] [rbp-38h] BYREF

  if ( SetEvent(Parameter[8]) )
  {
    pHandles[0] = Parameter[9];
    pHandles[1] = Parameter[11];
    while ( 1 )
    {
      v2 = MsgWaitForMultipleObjectsEx(2u, pHandles, 0xFFFFFFFF, 0x1CBFu, 2u);
      if ( !v2 )
        break;
      v3 = v2 - 1;
      if ( v3 )
      {
        v4 = v3 - 1;
        if ( v4 )
        {
          if ( v4 != 190 )
            break;
        }
        else
        {
          PeekMessageW(&Msg, 0, 0, 0, 0);
        }
      }
      else
      {
        CPimcManager::HandleTimer(*(_DWORD *)Parameter);
      }
    }
  }
  SetEvent(Parameter[10]);
  return 0;
}

```

## disassembly

```asm
0x18000ad10  push    rbx
0x18000ad12  sub     rsp, 70h
0x18000ad16  mov     rbx, rcx
0x18000ad19  mov     rcx, [rcx+40h]; hEvent
0x18000ad1d  call    cs:__imp_SetEvent
0x18000ad23  test    eax, eax
0x18000ad25  jz      short loc_18000AD70
0x18000ad27  mov     rax, [rbx+48h]
0x18000ad2b  mov     [rsp+78h+pHandles], rax
0x18000ad30  mov     rax, [rbx+58h]
0x18000ad34  mov     [rsp+78h+var_40], rax
0x18000ad39  mov     r9d, 1CBFh; dwWakeMask
0x18000ad3f  mov     [rsp+78h+dwFlags], 2; wRemoveMsg
0x18000ad47  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18000ad4b  lea     rdx, [rsp+78h+pHandles]; pHandles
0x18000ad50  mov     ecx, 2; nCount
0x18000ad55  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x18000ad5b  test    eax, eax
0x18000ad5d  jz      short loc_18000AD70
0x18000ad5f  sub     eax, 1
0x18000ad62  jz      short loc_18000AD9C
0x18000ad64  sub     eax, 1
0x18000ad67  jz      short loc_18000AD82
0x18000ad69  cmp     eax, 0BEh
0x18000ad6e  jz      short loc_18000AD39
0x18000ad70  mov     rcx, [rbx+50h]; hEvent
0x18000ad74  call    cs:__imp_SetEvent
0x18000ad7a  xor     eax, eax
0x18000ad7c  add     rsp, 70h
0x18000ad80  pop     rbx
0x18000ad81  retn
0x18000ad82  and     [rsp+78h+dwFlags], 0
0x18000ad87  lea     rcx, [rsp+78h+Msg]; lpMsg
0x18000ad8c  xor     r9d, r9d; wMsgFilterMax
0x18000ad8f  xor     r8d, r8d; wMsgFilterMin
0x18000ad92  xor     edx, edx; hWnd
0x18000ad94  call    cs:__imp_PeekMessageW
0x18000ad9a  jmp     short loc_18000AD39
0x18000ad9c  mov     ecx, [rbx]; unsigned int
0x18000ad9e  call    ?HandleTimer@CPimcManager@@SAXK@Z; CPimcManager::HandleTimer(ulong)
0x18000ada3  jmp     short loc_18000AD39
```
