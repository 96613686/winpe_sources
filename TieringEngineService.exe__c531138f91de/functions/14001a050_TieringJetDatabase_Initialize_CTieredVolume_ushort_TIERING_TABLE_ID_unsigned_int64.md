# TieringJetDatabase::Initialize(CTieredVolume *,ushort *,_TIERING_TABLE_ID,unsigned __int64 *)

- ea: `0x14001a050`
- end: `0x14001a1cb`
- name: `?Initialize@TieringJetDatabase@@QEAAJPEAVCTieredVolume@@PEAGW4_TIERING_TABLE_ID@@PEA_K@Z`
- size: `379`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400127dc`

## callees

- `0x140004ef0`
- `0x140005420`
- `0x140009c08`
- `0x14001a050`
- `0x14001cd80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a0fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a0fc`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14001a0da`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14001a0da`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001a0ee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001a0ee`

## string_xrefs

- `0x14001a0c6`: `TieringPinnedCacheFiles`

## pseudocode

```c
__int64 __fastcall TieringJetDatabase::Initialize(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  const wchar_t *v9; // rax
  void *v10; // rcx
  HANDLE EventW; // rbx
  signed int LastError; // eax
  _BYTE v14[8]; // [rsp+30h] [rbp-38h] BYREF
  int v15; // [rsp+38h] [rbp-30h]

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "TieringJetDatabase::Initialize";
  CHResultImp::CHResultImp((CHResultImp *)v14);
  *(_QWORD *)(a1 + 104) = a5;
  *(_QWORD *)a1 = a2;
  *(_DWORD *)(a1 + 96) = a4;
  *(_QWORD *)(a1 + 112) = a3;
  switch ( a4 )
  {
    case 1:
      v9 = L"TieringEngineHeat";
LABEL_7:
      *(_QWORD *)(a1 + 88) = v9;
      v10 = *(void **)(a1 + 80);
      if ( v10 )
      {
        ResetEvent(v10);
      }
      else
      {
        EventW = CreateEventW(0, 1, 0, 0);
        if ( !EventW )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v15 = LastError;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              61,
              (unsigned int)&WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
              *(_QWORD *)(a1 + 112),
              LastError);
          }
        }
        *(_QWORD *)(a1 + 80) = EventW;
      }
      *(_WORD *)(a1 + 76) = 0;
      *(_BYTE *)(a1 + 156) = 1;
      CHResultImp::~CHResultImp((CHResultImp *)v14);
      return 0;
    case 2:
      v9 = L"TieringPinnedFiles";
      goto LABEL_7;
    case 3:
      v9 = L"TieringPinnedCacheFiles";
      goto LABEL_7;
  }
  v15 = -2146881521;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_DSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      60,
      (unsigned int)&WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
      a4,
      a3,
      15);
  }
  CHResultImp::~CHResultImp((CHResultImp *)v14);
  return 2148085775LL;
}

```

## disassembly

```asm
0x14001a050  push    rbx
0x14001a052  push    rbp
0x14001a053  push    rsi
0x14001a054  push    rdi
0x14001a055  sub     rsp, 48h
0x14001a059  mov     rax, gs:58h
0x14001a062  mov     rdi, rcx
0x14001a065  mov     ecx, 8
0x14001a06a  mov     esi, r9d
0x14001a06d  mov     rbp, r8
0x14001a070  mov     rbx, rdx
0x14001a073  mov     r10, [rax]
0x14001a076  lea     rax, aTieringjetdata; "TieringJetDatabase::Initialize"
0x14001a07d  mov     [rcx+r10], rax
0x14001a081  lea     rcx, [rsp+68h+var_38]; this
0x14001a086  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14001a08b  mov     rax, [rsp+68h+arg_20]
0x14001a093  mov     [rdi+68h], rax
0x14001a097  mov     [rdi], rbx
0x14001a09a  mov     [rdi+60h], esi
0x14001a09d  mov     [rdi+70h], rbp
0x14001a0a1  cmp     esi, 1
0x14001a0a4  jnz     short loc_14001A0AF
0x14001a0a6  lea     rax, aTieringengineh; "TieringEngineHeat"
0x14001a0ad  jmp     short loc_14001A0CD
0x14001a0af  cmp     esi, 2
0x14001a0b2  jnz     short loc_14001A0BD
0x14001a0b4  lea     rax, aTieringpinnedf; "TieringPinnedFiles"
0x14001a0bb  jmp     short loc_14001A0CD
0x14001a0bd  cmp     esi, 3
0x14001a0c0  jnz     loc_14001A16D
0x14001a0c6  lea     rax, aTieringpinnedc; "TieringPinnedCacheFiles"
0x14001a0cd  mov     [rdi+58h], rax
0x14001a0d1  mov     rcx, [rdi+50h]; hEvent
0x14001a0d5  test    rcx, rcx
0x14001a0d8  jz      short loc_14001A0E2
0x14001a0da  call    cs:__imp_ResetEvent
0x14001a0e0  jmp     short loc_14001A152
0x14001a0e2  xor     r9d, r9d; lpName
0x14001a0e5  xor     r8d, r8d; bInitialState
0x14001a0e8  xor     ecx, ecx; lpEventAttributes
0x14001a0ea  lea     edx, [r9+1]; bManualReset
0x14001a0ee  call    cs:__imp_CreateEventW
0x14001a0f4  mov     rbx, rax
0x14001a0f7  test    rax, rax
0x14001a0fa  jnz     short loc_14001A14E
0x14001a0fc  call    cs:__imp_GetLastError
0x14001a102  test    eax, eax
0x14001a104  jle     short loc_14001A10E
0x14001a106  movzx   eax, ax
0x14001a109  or      eax, 80070000h
0x14001a10e  mov     [rsp+68h+var_30], eax
0x14001a112  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a119  lea     rdx, WPP_GLOBAL_Control
0x14001a120  cmp     rcx, rdx
0x14001a123  jz      short loc_14001A14E
0x14001a125  test    byte ptr [rcx+1Ch], 1
0x14001a129  jz      short loc_14001A14E
0x14001a12b  cmp     byte ptr [rcx+19h], 2
0x14001a12f  jb      short loc_14001A14E
0x14001a131  mov     r9, [rdi+70h]
0x14001a135  lea     r8, WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids
0x14001a13c  mov     rcx, [rcx+10h]
0x14001a140  mov     edx, 3Dh ; '='
0x14001a145  mov     dword ptr [rsp+68h+var_48], eax
0x14001a149  call    WPP_SF_Sd
0x14001a14e  mov     [rdi+50h], rbx
0x14001a152  lea     rcx, [rsp+68h+var_38]; this
0x14001a157  mov     word ptr [rdi+4Ch], 0
0x14001a15d  mov     byte ptr [rdi+9Ch], 1
0x14001a164  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14001a169  xor     eax, eax
0x14001a16b  jmp     short loc_14001A1C2
0x14001a16d  mov     ebx, 8009300Fh
0x14001a172  mov     [rsp+68h+var_30], ebx
0x14001a176  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a17d  lea     rdx, WPP_GLOBAL_Control
0x14001a184  cmp     rcx, rdx
0x14001a187  jz      short loc_14001A1B6
0x14001a189  test    byte ptr [rcx+1Ch], 1
0x14001a18d  jz      short loc_14001A1B6
0x14001a18f  cmp     byte ptr [rcx+19h], 2
0x14001a193  jb      short loc_14001A1B6
0x14001a195  mov     rcx, [rcx+10h]
0x14001a199  lea     r8, WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids
0x14001a1a0  mov     edx, 3Ch ; '<'
0x14001a1a5  mov     [rsp+68h+var_40], ebx
0x14001a1a9  mov     r9d, esi
0x14001a1ac  mov     [rsp+68h+var_48], rbp
0x14001a1b1  call    WPP_SF_DSd
0x14001a1b6  lea     rcx, [rsp+68h+var_38]; this
0x14001a1bb  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14001a1c0  mov     eax, ebx
0x14001a1c2  add     rsp, 48h
0x14001a1c6  pop     rdi
0x14001a1c7  pop     rsi
0x14001a1c8  pop     rbp
0x14001a1c9  pop     rbx
0x14001a1ca  retn
```
