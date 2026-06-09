# BfpCreateMappingInformation

- ea: `0x14001d194`
- end: `0x14001d2b8`
- name: `BfpCreateMappingInformation`
- size: `292`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140019c44`
- `0x14001cd84`

## callees

- `0x140001348`
- `0x140004cc0`
- `0x14001d130`
- `0x14001d194`
- `0x14001e998`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001d1b9`
- `ntoskrnl!ExAllocatePool2` at `0x14001d1b9`

## pseudocode

```c
__int64 __fastcall BfpCreateMappingInformation(__int64 a1, int a2, _QWORD *a3)
{
  __int64 Pool2; // rax
  _QWORD *v7; // rbx
  __int64 v8; // rcx
  _WORD *v9; // r14
  int v10; // edx
  int v11; // edx
  int UnicodeString; // edi
  size_t v13; // r8
  void *v14; // rcx

  Pool2 = ExAllocatePool2(256, 80, 1886209602);
  v7 = (_QWORD *)Pool2;
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  v8 = *(unsigned __int16 *)(a1 + 4);
  v9 = (_WORD *)(Pool2 + 16);
  v10 = *(unsigned __int16 *)(a1 + 2);
  if ( *(unsigned __int16 *)(a1 + 4) - v10 == 2 )
  {
    *v9 = 0;
    *(_QWORD *)(Pool2 + 24) = 0;
    goto LABEL_5;
  }
  LOWORD(v8) = v8 - v10;
  UnicodeString = BfAllocateUnicodeString(v8, v9);
  if ( UnicodeString >= 0 )
  {
    v13 = (unsigned __int16)(*(_WORD *)(a1 + 4) - *(_WORD *)(a1 + 2));
    v14 = (void *)v7[3];
    *v9 = v13;
    memmove(v14, (const void *)(a1 + 2 * (((unsigned __int64)*(unsigned __int16 *)(a1 + 2) >> 1) + 3)), v13);
LABEL_5:
    UnicodeString = 0;
    v7[9] = v7 + 8;
    v7[8] = v7 + 8;
    *((_DWORD *)v7 + 2) = a2;
    *((_BYTE *)v7 + 48) = 0;
    *v7 = 1;
    *a3 = v7;
    return (unsigned int)UnicodeString;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      8,
      18,
      (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
      92,
      UnicodeString);
  }
  BfpDeleteMappingInformation(v7);
  return (unsigned int)UnicodeString;
}

```

## disassembly

```asm
0x14001d194  push    rbx
0x14001d196  push    rbp
0x14001d197  push    rsi
0x14001d198  push    rdi
0x14001d199  push    r14
0x14001d19b  push    r15
0x14001d19d  sub     rsp, 48h
0x14001d1a1  mov     r15, r8
0x14001d1a4  mov     ebp, edx
0x14001d1a6  mov     rsi, rcx
0x14001d1a9  mov     edx, 50h ; 'P'
0x14001d1ae  mov     ecx, 100h
0x14001d1b3  mov     r8d, 706D4642h
0x14001d1b9  call    cs:__imp_ExAllocatePool2
0x14001d1c0  nop     dword ptr [rax+rax+00h]
0x14001d1c5  mov     rbx, rax
0x14001d1c8  test    rax, rax
0x14001d1cb  jz      short loc_14001D249
0x14001d1cd  movzx   ecx, word ptr [rsi+4]
0x14001d1d1  lea     r14, [rax+10h]
0x14001d1d5  movzx   edx, word ptr [rsi+2]
0x14001d1d9  mov     eax, ecx
0x14001d1db  sub     eax, edx
0x14001d1dd  cmp     eax, 2
0x14001d1e0  jz      short loc_14001D250
0x14001d1e2  sub     cx, dx
0x14001d1e5  mov     rdx, r14
0x14001d1e8  call    BfAllocateUnicodeString
0x14001d1ed  mov     edi, eax
0x14001d1ef  test    eax, eax
0x14001d1f1  js      short loc_14001D25C
0x14001d1f3  movzx   ecx, word ptr [rsi+4]
0x14001d1f7  sub     cx, [rsi+2]
0x14001d1fb  movzx   r8d, cx; Size
0x14001d1ff  mov     rcx, [rbx+18h]; void *
0x14001d203  mov     [r14], r8w
0x14001d207  movzx   eax, word ptr [rsi+2]
0x14001d20b  shr     rax, 1
0x14001d20e  add     rax, 3
0x14001d212  lea     rdx, [rsi+rax*2]; Src
0x14001d216  call    memmove
0x14001d21b  lea     rax, [rbx+40h]
0x14001d21f  xor     edi, edi
0x14001d221  mov     [rax+8], rax
0x14001d225  mov     [rax], rax
0x14001d228  mov     [rbx+8], ebp
0x14001d22b  mov     byte ptr [rbx+30h], 0
0x14001d22f  mov     qword ptr [rbx], 1
0x14001d236  mov     [r15], rbx
0x14001d239  mov     eax, edi
0x14001d23b  add     rsp, 48h
0x14001d23f  pop     r15
0x14001d241  pop     r14
0x14001d243  pop     rdi
0x14001d244  pop     rsi
0x14001d245  pop     rbp
0x14001d246  pop     rbx
0x14001d247  retn
0x14001d249  mov     edi, 0C000009Ah
0x14001d24e  jmp     short loc_14001D239
0x14001d250  xor     eax, eax
0x14001d252  mov     [r14], ax
0x14001d256  mov     [rbx+18h], rax
0x14001d25a  jmp     short loc_14001D21B
0x14001d25c  lea     rax, WPP_RECORDER_INITIALIZED
0x14001d263  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001d26a  jnz     short loc_14001D276
0x14001d26c  mov     rcx, rbx; P
0x14001d26f  call    BfpDeleteMappingInformation
0x14001d274  jmp     short loc_14001D239
0x14001d276  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d27d  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001d284  mov     [rsp+78h+var_40], edi
0x14001d288  mov     r9d, 12h
0x14001d28e  mov     [rsp+78h+var_48], 35Ch
0x14001d296  mov     dl, 2
0x14001d298  mov     [rsp+78h+var_50], rax
0x14001d29d  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x14001d2a4  mov     rcx, [rcx+40h]
0x14001d2a8  lea     r8d, [r9-0Ah]
0x14001d2ac  mov     [rsp+78h+var_58], rax
0x14001d2b1  call    WPP_RECORDER_SF_sDd
0x14001d2b6  jmp     short loc_14001D26C
```
