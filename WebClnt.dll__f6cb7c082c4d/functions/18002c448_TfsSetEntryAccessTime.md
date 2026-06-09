# TfsSetEntryAccessTime

- ea: `0x18002c448`
- end: `0x18002c585`
- name: `TfsSetEntryAccessTime`
- size: `317`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001507c`

## callees

- `0x18000b7dc`
- `0x18000b93c`
- `0x18002afb0`
- `0x18002c448`
- `0x18002cda0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c4d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c52f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c56d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c4d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c52f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c56d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c487`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c487`

## pseudocode

```c
__int64 __fastcall TfsSetEntryAccessTime(__int64 a1, const wchar_t *a2, __int64 a3)
{
  HLOCAL v3; // rsi
  struct _RTL_CRITICAL_SECTION *v7; // rdi
  unsigned int Entry; // eax
  unsigned int v9; // esi
  __int64 v10; // [rsp+50h] [rbp+8h] BYREF
  __int64 v11; // [rsp+60h] [rbp+18h]

  v11 = a3;
  v3 = DavTfsStore;
  v10 = 0;
  if ( !DavTfsStore )
    return 6;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)DavTfsStore + 56);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)DavTfsStore + 56));
  Entry = TfsFindEntry((__int64)v3, a2, &v10);
  v9 = Entry;
  if ( Entry )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids, Entry);
    LeaveCriticalSection(v7);
    return v9;
  }
  else if ( v10 && *(_DWORD *)(v10 + 24) == 1 )
  {
    *(_QWORD *)(v10 + 88) = a3;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_qdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 56);
    LeaveCriticalSection(v7);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids, a2);
    LeaveCriticalSection(v7);
    return 2;
  }
}

```

## disassembly

```asm
0x18002c448  mov     rax, rsp
0x18002c44b  mov     [rax+10h], rbx
0x18002c44f  mov     [rax+18h], r8
0x18002c453  mov     [rax+8], rcx
0x18002c457  push    rbp
0x18002c458  push    rsi
0x18002c459  push    rdi
0x18002c45a  sub     rsp, 30h
0x18002c45e  mov     rsi, cs:DavTfsStore
0x18002c465  mov     rbx, r8
0x18002c468  mov     qword ptr [rax+8], 0
0x18002c470  mov     rbp, rdx
0x18002c473  test    rsi, rsi
0x18002c476  jnz     short loc_18002C480
0x18002c478  lea     eax, [rsi+6]
0x18002c47b  jmp     loc_18002C578
0x18002c480  lea     rdi, [rsi+38h]
0x18002c484  mov     rcx, rdi; lpCriticalSection
0x18002c487  call    cs:__imp_EnterCriticalSection
0x18002c48d  lea     r8, [rsp+48h+arg_0]
0x18002c492  mov     rdx, rbp
0x18002c495  mov     rcx, rsi
0x18002c498  call    TfsFindEntry
0x18002c49d  mov     esi, eax
0x18002c49f  test    eax, eax
0x18002c4a1  jz      short loc_18002C4E4
0x18002c4a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c4aa  lea     rdx, WPP_GLOBAL_Control
0x18002c4b1  cmp     rcx, rdx
0x18002c4b4  jz      short loc_18002C4D4
0x18002c4b6  test    byte ptr [rcx+1Ch], 1
0x18002c4ba  jz      short loc_18002C4D4
0x18002c4bc  mov     rcx, [rcx+10h]
0x18002c4c0  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002c4c7  mov     edx, 36h ; '6'
0x18002c4cc  mov     r9d, eax
0x18002c4cf  call    WPP_SF_d
0x18002c4d4  mov     rcx, rdi; lpCriticalSection
0x18002c4d7  call    cs:__imp_LeaveCriticalSection
0x18002c4dd  mov     eax, esi
0x18002c4df  jmp     loc_18002C578
0x18002c4e4  mov     r9, [rsp+48h+arg_0]
0x18002c4e9  test    r9, r9
0x18002c4ec  jz      short loc_18002C539
0x18002c4ee  cmp     dword ptr [r9+18h], 1
0x18002c4f3  jnz     short loc_18002C539
0x18002c4f5  mov     [r9+58h], rbx
0x18002c4f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c500  lea     rdx, WPP_GLOBAL_Control
0x18002c507  cmp     rcx, rdx
0x18002c50a  jz      short loc_18002C52C
0x18002c50c  test    byte ptr [rcx+1Ch], 2
0x18002c510  jz      short loc_18002C52C
0x18002c512  mov     eax, [rsp+48h+arg_14]
0x18002c516  mov     edx, 38h ; '8'
0x18002c51b  mov     rcx, [rcx+10h]
0x18002c51f  mov     [rsp+48h+var_20], ebx
0x18002c523  mov     [rsp+48h+var_28], eax
0x18002c527  call    WPP_SF_qdd
0x18002c52c  mov     rcx, rdi; lpCriticalSection
0x18002c52f  call    cs:__imp_LeaveCriticalSection
0x18002c535  xor     eax, eax
0x18002c537  jmp     short loc_18002C578
0x18002c539  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c540  lea     rdx, WPP_GLOBAL_Control
0x18002c547  cmp     rcx, rdx
0x18002c54a  jz      short loc_18002C56A
0x18002c54c  test    byte ptr [rcx+1Ch], 1
0x18002c550  jz      short loc_18002C56A
0x18002c552  mov     rcx, [rcx+10h]
0x18002c556  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002c55d  mov     edx, 37h ; '7'
0x18002c562  mov     r9, rbp
0x18002c565  call    WPP_SF_S
0x18002c56a  mov     rcx, rdi; lpCriticalSection
0x18002c56d  call    cs:__imp_LeaveCriticalSection
0x18002c573  mov     eax, 2
0x18002c578  mov     rbx, [rsp+48h+arg_8]
0x18002c57d  add     rsp, 30h
0x18002c581  pop     rdi
0x18002c582  pop     rsi
0x18002c583  pop     rbp
0x18002c584  retn
```
