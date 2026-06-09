# TfsReleaseEntry

- ea: `0x18002be24`
- end: `0x18002bf9c`
- name: `TfsReleaseEntry`
- size: `376`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x18001507c`
- `0x1800169d4`
- `0x180017624`
- `0x18001f190`
- `0x1800252d0`

## callees

- `0x18000b7dc`
- `0x18000b93c`
- `0x18000bc5c`
- `0x180014f50`
- `0x18002afb0`
- `0x18002be24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002beae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bf43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bf81`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002beae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bf43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bf81`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002be5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002be5e`

## pseudocode

```c
__int64 __fastcall TfsReleaseEntry(__int64 a1, __int64 a2)
{
  HLOCAL v2; // rdi
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  unsigned int Entry; // eax
  unsigned int v7; // edi
  __int64 v8; // r9
  int v9; // eax
  int v10; // eax
  __int64 v11; // [rsp+40h] [rbp+8h] BYREF

  v2 = DavTfsStore;
  v11 = 0;
  if ( !DavTfsStore )
    return 6;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)DavTfsStore + 56);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)DavTfsStore + 56));
  Entry = TfsFindEntry(v2, a2, &v11);
  v7 = Entry;
  if ( Entry )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids, Entry);
    LeaveCriticalSection(v5);
    return v7;
  }
  else
  {
    v8 = v11;
    if ( !v11 || *(_DWORD *)(v11 + 24) == 2 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids, a2);
      LeaveCriticalSection(v5);
      return 2;
    }
    else
    {
      v9 = *(_DWORD *)(v11 + 20);
      if ( v9 )
      {
        v10 = v9 - 1;
        *(_DWORD *)(v11 + 20) = v10;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids, v8, v10);
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids, v11);
      }
      LeaveCriticalSection(v5);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x18002be24  mov     rax, rsp
0x18002be27  mov     [rax+10h], rbx
0x18002be2b  mov     [rax+18h], rsi
0x18002be2f  mov     [rax+8], rcx
0x18002be33  push    rdi
0x18002be34  sub     rsp, 30h
0x18002be38  mov     rdi, cs:DavTfsStore
0x18002be3f  mov     rsi, rdx
0x18002be42  mov     qword ptr [rax+8], 0
0x18002be4a  test    rdi, rdi
0x18002be4d  jnz     short loc_18002BE57
0x18002be4f  lea     eax, [rdi+6]
0x18002be52  jmp     loc_18002BF8C
0x18002be57  lea     rbx, [rdi+38h]
0x18002be5b  mov     rcx, rbx; lpCriticalSection
0x18002be5e  call    cs:__imp_EnterCriticalSection
0x18002be64  lea     r8, [rsp+38h+arg_0]
0x18002be69  mov     rdx, rsi
0x18002be6c  mov     rcx, rdi
0x18002be6f  call    TfsFindEntry
0x18002be74  mov     edi, eax
0x18002be76  test    eax, eax
0x18002be78  jz      short loc_18002BEBB
0x18002be7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be81  lea     rdx, WPP_GLOBAL_Control
0x18002be88  cmp     rcx, rdx
0x18002be8b  jz      short loc_18002BEAB
0x18002be8d  test    byte ptr [rcx+1Ch], 1
0x18002be91  jz      short loc_18002BEAB
0x18002be93  mov     rcx, [rcx+10h]
0x18002be97  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002be9e  mov     edx, 3Ch ; '<'
0x18002bea3  mov     r9d, eax
0x18002bea6  call    WPP_SF_d
0x18002beab  mov     rcx, rbx; lpCriticalSection
0x18002beae  call    cs:__imp_LeaveCriticalSection
0x18002beb4  mov     eax, edi
0x18002beb6  jmp     loc_18002BF8C
0x18002bebb  mov     r9, [rsp+38h+arg_0]
0x18002bec0  test    r9, r9
0x18002bec3  jz      loc_18002BF4D
0x18002bec9  cmp     dword ptr [r9+18h], 2
0x18002bece  jz      short loc_18002BF4D
0x18002bed0  mov     eax, [r9+14h]
0x18002bed4  test    eax, eax
0x18002bed6  jz      short loc_18002BF12
0x18002bed8  dec     eax
0x18002beda  mov     [r9+14h], eax
0x18002bede  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bee5  lea     rdx, WPP_GLOBAL_Control
0x18002beec  cmp     rcx, rdx
0x18002beef  jz      short loc_18002BF40
0x18002bef1  test    byte ptr [rcx+1Ch], 2
0x18002bef5  jz      short loc_18002BF40
0x18002bef7  mov     rcx, [rcx+10h]
0x18002befb  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002bf02  mov     edx, 3Eh ; '>'
0x18002bf07  mov     [rsp+38h+var_18], eax
0x18002bf0b  call    WPP_SF_qd
0x18002bf10  jmp     short loc_18002BF40
0x18002bf12  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf19  lea     rdx, WPP_GLOBAL_Control
0x18002bf20  cmp     rcx, rdx
0x18002bf23  jz      short loc_18002BF40
0x18002bf25  test    byte ptr [rcx+1Ch], 1
0x18002bf29  jz      short loc_18002BF40
0x18002bf2b  mov     rcx, [rcx+10h]
0x18002bf2f  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002bf36  mov     edx, 3Fh ; '?'
0x18002bf3b  call    WPP_SF_q
0x18002bf40  mov     rcx, rbx; lpCriticalSection
0x18002bf43  call    cs:__imp_LeaveCriticalSection
0x18002bf49  xor     eax, eax
0x18002bf4b  jmp     short loc_18002BF8C
0x18002bf4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf54  lea     rdx, WPP_GLOBAL_Control
0x18002bf5b  cmp     rcx, rdx
0x18002bf5e  jz      short loc_18002BF7E
0x18002bf60  test    byte ptr [rcx+1Ch], 1
0x18002bf64  jz      short loc_18002BF7E
0x18002bf66  mov     rcx, [rcx+10h]
0x18002bf6a  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002bf71  mov     edx, 3Dh ; '='
0x18002bf76  mov     r9, rsi
0x18002bf79  call    WPP_SF_S
0x18002bf7e  mov     rcx, rbx; lpCriticalSection
0x18002bf81  call    cs:__imp_LeaveCriticalSection
0x18002bf87  mov     eax, 2
0x18002bf8c  mov     rbx, [rsp+38h+arg_8]
0x18002bf91  mov     rsi, [rsp+38h+arg_10]
0x18002bf96  add     rsp, 30h
0x18002bf9a  pop     rdi
0x18002bf9b  retn
```
