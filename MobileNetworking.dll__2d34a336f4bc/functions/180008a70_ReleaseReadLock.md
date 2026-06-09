# ReleaseReadLock

- ea: `0x180008a70`
- end: `0x180008af9`
- name: `ReleaseReadLock`
- size: `137`
- prototype: `signed __int32 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180008a70`
- `0x180008ff0`
- `0x180009130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008abe`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008abe`

## pseudocode

```c
signed __int32 __fastcall ReleaseReadLock(__int64 a1)
{
  signed __int32 result; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_ae89183a349339de188038c4f0a19280_Traceguids);
  result = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 48), 0xFFFFFFFF);
  if ( result - 1 < 0 )
    result = SetEvent(*(HANDLE *)(a1 + 56));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    return WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_ae89183a349339de188038c4f0a19280_Traceguids, 0);
  return result;
}

```

## disassembly

```asm
0x180008a70  mov     [rsp+arg_0], rbx
0x180008a75  push    rdi
0x180008a76  sub     rsp, 20h
0x180008a7a  mov     rbx, rcx
0x180008a7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a84  lea     rdi, WPP_GLOBAL_Control
0x180008a8b  cmp     rcx, rdi
0x180008a8e  jz      short loc_180008AAB
0x180008a90  test    byte ptr [rcx+1Ch], 8
0x180008a94  jz      short loc_180008AAB
0x180008a96  mov     rcx, [rcx+10h]
0x180008a9a  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x180008aa1  mov     edx, 14h
0x180008aa6  call    WPP_SF_
0x180008aab  mov     eax, 0FFFFFFFFh
0x180008ab0  lock xadd [rbx+30h], eax
0x180008ab5  cmp     eax, 1
0x180008ab8  jns     short loc_180008AC4
0x180008aba  mov     rcx, [rbx+38h]; hEvent
0x180008abe  call    cs:__imp_SetEvent
0x180008ac4  mov     rcx, cs:WPP_GLOBAL_Control
0x180008acb  cmp     rcx, rdi
0x180008ace  jz      short loc_180008AEE
0x180008ad0  test    byte ptr [rcx+1Ch], 8
0x180008ad4  jz      short loc_180008AEE
0x180008ad6  mov     rcx, [rcx+10h]
0x180008ada  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x180008ae1  mov     edx, 15h
0x180008ae6  xor     r9d, r9d
0x180008ae9  call    WPP_SF_L
0x180008aee  mov     rbx, [rsp+28h+arg_0]
0x180008af3  add     rsp, 20h
0x180008af7  pop     rdi
0x180008af8  retn
```
