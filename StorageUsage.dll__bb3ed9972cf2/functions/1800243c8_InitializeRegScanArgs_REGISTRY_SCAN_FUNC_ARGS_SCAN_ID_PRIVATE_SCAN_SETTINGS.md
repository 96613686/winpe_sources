# InitializeRegScanArgs(REGISTRY_SCAN_FUNC_ARGS *,SCAN_ID,PRIVATE_SCAN_SETTINGS &)

- ea: `0x1800243c8`
- end: `0x1800244ce`
- name: `?InitializeRegScanArgs@@YAJPEAUREGISTRY_SCAN_FUNC_ARGS@@W4SCAN_ID@@AEAUPRIVATE_SCAN_SETTINGS@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002475c`

## callees

- `0x1800152d4`
- `0x180016e60`
- `0x18001f788`
- `0x1800243c8`

## pseudocode

```c
__int64 __fastcall InitializeRegScanArgs(__int64 a1, int a2)
{
  int v3; // edi
  __int64 v4; // rdx
  __int64 result; // rax
  int v6; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_DWORD *)a1 = a2;
  *(_WORD *)(a1 + 4) = 0;
  v3 = AllocateMemory<unsigned short>(a1 + 40);
  if ( v3 < 0 )
  {
    v4 = 326;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\regscanner.cpp",
      (const char *)(unsigned int)v3,
      v6);
    return (unsigned int)v3;
  }
  *(_DWORD *)(a1 + 32) = 0x80000000;
  v3 = AllocateMemory<enum SCAN_ID>(a1 + 24, 200);
  if ( v3 < 0 )
  {
    v4 = 330;
    goto LABEL_3;
  }
  v3 = AllocateMemory<enum SCAN_ID>(a1 + 16, 200);
  if ( v3 < 0 )
  {
    v4 = 332;
    goto LABEL_3;
  }
  *(_WORD *)(a1 + 8) = 0;
  v3 = AllocateMemory<unsigned short>(a1 + 64);
  if ( v3 < 0 )
  {
    v4 = 344;
    goto LABEL_3;
  }
  *(_DWORD *)(a1 + 56) = 0x80000000;
  v3 = AllocateMemory<enum SCAN_ID>(a1 + 72, 200);
  if ( v3 < 0 )
  {
    v4 = 348;
    goto LABEL_3;
  }
  v3 = AllocateMemory<enum SCAN_ID>(a1 + 80, 200);
  if ( v3 < 0 )
  {
    v4 = 350;
    goto LABEL_3;
  }
  v3 = AllocateMemory<enum SCAN_ID>(a1 + 88, 200);
  if ( v3 < 0 )
  {
    v4 = 352;
    goto LABEL_3;
  }
  result = 0;
  *(_WORD *)(a1 + 48) = 0;
  return result;
}

```

## disassembly

```asm
0x1800243c8  push    rbx
0x1800243ca  push    rbp
0x1800243cb  push    rsi
0x1800243cc  push    rdi
0x1800243cd  sub     rsp, 28h
0x1800243d1  xor     eax, eax
0x1800243d3  mov     [rcx], edx
0x1800243d5  mov     [rcx+4], ax
0x1800243d9  mov     rbx, rcx
0x1800243dc  add     rcx, 28h ; '('
0x1800243e0  call    ??$AllocateMemory@G@@YAJPEAPEAG_K@Z; AllocateMemory<ushort>(ushort * *,unsigned __int64)
0x1800243e5  mov     edi, eax
0x1800243e7  test    eax, eax
0x1800243e9  jns     short loc_18002440B
0x1800243eb  mov     edx, 146h; void *
0x1800243f0  mov     rcx, [rsp+48h]; this
0x1800243f5  lea     r8, aOnecoreDrivers_3; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800243fc  mov     r9d, edi; char *
0x1800243ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024404  mov     eax, edi
0x180024406  jmp     loc_1800244C5
0x18002440b  mov     esi, 0C8h
0x180024410  mov     dword ptr [rbx+20h], 80000000h
0x180024417  mov     edx, esi
0x180024419  lea     rcx, [rbx+18h]
0x18002441d  call    ??$AllocateMemory@W4SCAN_ID@@@@YAJPEAPEAW4SCAN_ID@@_K@Z; AllocateMemory<SCAN_ID>(SCAN_ID * *,unsigned __int64)
0x180024422  mov     edi, eax
0x180024424  test    eax, eax
0x180024426  jns     short loc_18002442F
0x180024428  mov     edx, 14Ah
0x18002442d  jmp     short loc_1800243F0
0x18002442f  lea     rcx, [rbx+10h]
0x180024433  mov     rdx, rsi
0x180024436  call    ??$AllocateMemory@W4SCAN_ID@@@@YAJPEAPEAW4SCAN_ID@@_K@Z; AllocateMemory<SCAN_ID>(SCAN_ID * *,unsigned __int64)
0x18002443b  mov     edi, eax
0x18002443d  test    eax, eax
0x18002443f  jns     short loc_180024448
0x180024441  mov     edx, 14Ch
0x180024446  jmp     short loc_1800243F0
0x180024448  xor     eax, eax
0x18002444a  lea     rcx, [rbx+40h]
0x18002444e  mov     [rbx+8], ax
0x180024452  call    ??$AllocateMemory@G@@YAJPEAPEAG_K@Z; AllocateMemory<ushort>(ushort * *,unsigned __int64)
0x180024457  mov     edi, eax
0x180024459  test    eax, eax
0x18002445b  jns     short loc_180024464
0x18002445d  mov     edx, 158h
0x180024462  jmp     short loc_1800243F0
0x180024464  lea     rcx, [rbx+48h]
0x180024468  mov     dword ptr [rbx+38h], 80000000h
0x18002446f  mov     rdx, rsi
0x180024472  call    ??$AllocateMemory@W4SCAN_ID@@@@YAJPEAPEAW4SCAN_ID@@_K@Z; AllocateMemory<SCAN_ID>(SCAN_ID * *,unsigned __int64)
0x180024477  mov     edi, eax
0x180024479  test    eax, eax
0x18002447b  jns     short loc_180024487
0x18002447d  mov     edx, 15Ch
0x180024482  jmp     loc_1800243F0
0x180024487  lea     rcx, [rbx+50h]
0x18002448b  mov     rdx, rsi
0x18002448e  call    ??$AllocateMemory@W4SCAN_ID@@@@YAJPEAPEAW4SCAN_ID@@_K@Z; AllocateMemory<SCAN_ID>(SCAN_ID * *,unsigned __int64)
0x180024493  mov     edi, eax
0x180024495  test    eax, eax
0x180024497  jns     short loc_1800244A3
0x180024499  mov     edx, 15Eh
0x18002449e  jmp     loc_1800243F0
0x1800244a3  lea     rcx, [rbx+58h]
0x1800244a7  mov     rdx, rsi
0x1800244aa  call    ??$AllocateMemory@W4SCAN_ID@@@@YAJPEAPEAW4SCAN_ID@@_K@Z; AllocateMemory<SCAN_ID>(SCAN_ID * *,unsigned __int64)
0x1800244af  mov     edi, eax
0x1800244b1  test    eax, eax
0x1800244b3  jns     short loc_1800244BF
0x1800244b5  mov     edx, 160h
0x1800244ba  jmp     loc_1800243F0
0x1800244bf  xor     eax, eax
0x1800244c1  mov     [rbx+30h], ax
0x1800244c5  add     rsp, 28h
0x1800244c9  pop     rdi
0x1800244ca  pop     rsi
0x1800244cb  pop     rbp
0x1800244cc  pop     rbx
0x1800244cd  retn
```
