# PpdParseTextFile

- ea: `0x1800564d8`
- end: `0x18005673b`
- name: `PpdParseTextFile`
- size: `611`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18005c098`

## callees

- `0x1800552c0`
- `0x180056188`
- `0x180056244`
- `0x1800562c0`
- `0x1800564d8`
- `0x180056798`
- `0x180058498`
- `0x180058598`
- `0x18005c434`

## import_xrefs

- `KERNEL32!GetUserDefaultUILanguage` at `0x1800566c3`
- `KERNEL32!GetUserDefaultUILanguage` at `0x1800566c3`
- `KERNEL32!HeapAlloc` at `0x18005650d`
- `KERNEL32!HeapAlloc` at `0x1800565e6`
- `KERNEL32!HeapAlloc` at `0x1800565fd`
- `KERNEL32!HeapAlloc` at `0x18005650d`
- `KERNEL32!HeapAlloc` at `0x1800565e6`
- `KERNEL32!HeapAlloc` at `0x1800565fd`
- `KERNEL32!HeapCreate` at `0x1800564ed`
- `KERNEL32!HeapCreate` at `0x1800564ed`
- `KERNEL32!HeapDestroy` at `0x18005672a`
- `KERNEL32!HeapDestroy` at `0x18005672a`
- `KERNEL32!LocalAlloc` at `0x1800566ec`
- `KERNEL32!LocalAlloc` at `0x1800566ec`

## pseudocode

```c
HLOCAL __fastcall PpdParseTextFile(WCHAR *a1, int a2)
{
  HANDLE v4; // rax
  void *v5; // rbx
  _QWORD *v6; // rax
  __int64 v7; // rdi
  LPVOID v8; // rax
  void *v9; // rcx
  LPVOID v10; // rax
  bool v11; // zf
  __int64 i; // rcx
  int v13; // edx
  char *j; // r8
  HLOCAL v15; // rbx
  int v16; // eax
  __int64 v17; // rbx
  HLOCAL v18; // rax

  v4 = HeapCreate(0, 0, 0);
  v5 = v4;
  if ( !v4 )
    return 0;
  v6 = HeapAlloc(v4, 8u, 0x438u);
  v7 = (__int64)v6;
  if ( !v6 )
  {
    HeapDestroy(v5);
    return 0;
  }
  v6[1] = v5;
  v6[134] = v6;
  *v6 = v6;
  *((_DWORD *)v6 + 22) = -1;
  *((_DWORD *)v6 + 85) = 176128;
  *((_DWORD *)v6 + 87) = 0;
  *((_DWORD *)v6 + 88) = 300;
  *((_DWORD *)v6 + 133) = -1;
  *((_DWORD *)v6 + 134) = -1;
  *((_DWORD *)v6 + 132) = -1;
  *((_WORD *)v6 + 262) = 0;
  v6[71] = (char *)v6 + 628;
  v6[73] = (char *)v6 + 692;
  v6[75] = (char *)v6 + 756;
  *((_DWORD *)v6 + 101) = 2;
  v6[70] = 64;
  v6[72] = 64;
  v6[74] = 256;
  if ( (unsigned int)IGrowValueBuffer(v6 + 76)
    || (v8 = HeapAlloc(*(HANDLE *)(v7 + 8), 8u, 0x18Cu),
        v9 = *(void **)(v7 + 8),
        *(_QWORD *)(v7 + 24) = v8,
        v10 = HeapAlloc(v9, 8u, 0x63u),
        v11 = *(_QWORD *)(v7 + 24) == 0,
        *(_QWORD *)(v7 + 32) = v10,
        v11)
    || !v10 )
  {
    VFreeParserData(v7);
    return 0;
  }
  for ( i = 0; i != 99; ++i )
  {
    v13 = 0;
    for ( j = (&gPpdBuiltInKeywordTable)[3 * i]; *j; ++j )
      v13 = (unsigned __int8)*j ^ (2 * v13);
    *(_DWORD *)(*(_QWORD *)(v7 + 24) + 4 * i) = v13;
  }
  v15 = 0;
  v16 = IParseFile(v7, a1);
  if ( !v16 || v16 == -3 )
  {
    *(_DWORD *)(v7 + 40) = 0;
    if ( (unsigned int)BPackBinaryData(v7, a2) )
    {
      v17 = *(_QWORD *)(v7 + 1048);
      *(_DWORD *)(v17 + 12) = dwComputeFeatureOptionChecksum(v7);
      *(_DWORD *)(*(_QWORD *)(v7 + 1056) + 264LL) = dwCalcMaxKeywordSize(v7, 0);
      *(_DWORD *)(*(_QWORD *)(v7 + 1056) + 268LL) = dwCalcMaxKeywordSize(v7, 1);
      *(_DWORD *)(*(_QWORD *)(v7 + 1064) + 220LL) = GetUserDefaultUILanguage();
      BSaveBinaryDataToFile(v7, a1);
      v18 = LocalAlloc(0, *(unsigned int *)(v7 + 1040));
      v15 = v18;
      if ( v18 )
        memcpy_0(v18, *(const void **)(v7 + 1024), *(unsigned int *)(v7 + 1040));
    }
  }
  VFreeParserData(v7);
  return v15;
}

```

## disassembly

```asm
0x1800564d8  push    rbx
0x1800564da  push    rbp
0x1800564db  push    rsi
0x1800564dc  push    rdi
0x1800564dd  sub     rsp, 28h
0x1800564e1  mov     ebp, edx
0x1800564e3  mov     rsi, rcx
0x1800564e6  xor     edx, edx; dwInitialSize
0x1800564e8  xor     ecx, ecx; flOptions
0x1800564ea  xor     r8d, r8d; dwMaximumSize
0x1800564ed  call    cs:__imp_HeapCreate
0x1800564f3  mov     rbx, rax
0x1800564f6  test    rax, rax
0x1800564f9  jz      loc_180056730
0x1800564ff  mov     edx, 8; dwFlags
0x180056504  mov     r8d, 438h; dwBytes
0x18005650a  mov     rcx, rax; hHeap
0x18005650d  call    cs:__imp_HeapAlloc
0x180056513  mov     rdi, rax
0x180056516  test    rax, rax
0x180056519  jz      loc_180056727
0x18005651f  mov     [rax+8], rbx
0x180056523  lea     rcx, [rdi+260h]
0x18005652a  mov     [rax+430h], rax
0x180056531  mov     [rax], rax
0x180056534  mov     dword ptr [rax+58h], 0FFFFFFFFh
0x18005653b  mov     dword ptr [rax+154h], 2B000h
0x180056545  mov     dword ptr [rax+15Ch], 0
0x18005654f  mov     dword ptr [rax+160h], 12Ch
0x180056559  or      eax, 0FFFFFFFFh
0x18005655c  mov     [rdi+214h], eax
0x180056562  mov     [rdi+218h], eax
0x180056568  mov     [rdi+210h], eax
0x18005656e  xor     eax, eax
0x180056570  mov     [rdi+20Ch], ax
0x180056577  lea     rax, [rdi+274h]
0x18005657e  mov     [rdi+238h], rax
0x180056585  lea     rax, [rdi+2B4h]
0x18005658c  mov     [rdi+248h], rax
0x180056593  lea     rax, [rdi+2F4h]
0x18005659a  mov     [rdi+258h], rax
0x1800565a1  mov     dword ptr [rdi+194h], 2
0x1800565ab  mov     qword ptr [rdi+230h], 40h ; '@'
0x1800565b6  mov     qword ptr [rdi+240h], 40h ; '@'
0x1800565c1  mov     qword ptr [rdi+250h], 100h
0x1800565cc  call    IGrowValueBuffer
0x1800565d1  test    eax, eax
0x1800565d3  jnz     loc_18005671D
0x1800565d9  mov     rcx, [rdi+8]; hHeap
0x1800565dd  lea     edx, [rax+8]; dwFlags
0x1800565e0  mov     r8d, 18Ch; dwBytes
0x1800565e6  call    cs:__imp_HeapAlloc
0x1800565ec  mov     rcx, [rdi+8]; hHeap
0x1800565f0  mov     edx, 8; dwFlags
0x1800565f5  mov     [rdi+18h], rax
0x1800565f9  lea     r8d, [rdx+5Bh]; dwBytes
0x1800565fd  call    cs:__imp_HeapAlloc
0x180056603  cmp     qword ptr [rdi+18h], 0
0x180056608  mov     [rdi+20h], rax
0x18005660c  jz      loc_18005671D
0x180056612  test    rax, rax
0x180056615  jz      loc_18005671D
0x18005661b  xor     ecx, ecx
0x18005661d  lea     rax, [rcx+rcx*2]
0x180056621  xor     edx, edx
0x180056623  lea     r8, gPpdBuiltInKeywordTable
0x18005662a  mov     r8, [r8+rax*8]
0x18005662e  jmp     short loc_18005663A
0x180056630  add     edx, edx
0x180056632  movzx   eax, al
0x180056635  xor     edx, eax
0x180056637  inc     r8
0x18005663a  mov     al, [r8]
0x18005663d  test    al, al
0x18005663f  jnz     short loc_180056630
0x180056641  mov     rax, [rdi+18h]
0x180056645  mov     [rax+rcx*4], edx
0x180056648  inc     rcx
0x18005664b  cmp     rcx, 63h ; 'c'
0x18005664f  jnz     short loc_18005661D
0x180056651  mov     rdx, rsi
0x180056654  mov     rcx, rdi
0x180056657  xor     ebx, ebx
0x180056659  call    IParseFile
0x18005665e  test    eax, eax
0x180056660  jz      short loc_18005666B
0x180056662  cmp     eax, 0FFFFFFFDh
0x180056665  jnz     loc_180056710
0x18005666b  mov     edx, ebp
0x18005666d  mov     [rdi+28h], ebx
0x180056670  mov     rcx, rdi
0x180056673  call    BPackBinaryData
0x180056678  test    eax, eax
0x18005667a  jz      loc_180056710
0x180056680  mov     rbx, [rdi+418h]
0x180056687  mov     rcx, rdi
0x18005668a  call    dwComputeFeatureOptionChecksum
0x18005668f  xor     edx, edx
0x180056691  mov     [rbx+0Ch], eax
0x180056694  mov     rcx, rdi
0x180056697  call    dwCalcMaxKeywordSize
0x18005669c  mov     rcx, [rdi+420h]
0x1800566a3  mov     edx, 1
0x1800566a8  mov     [rcx+108h], eax
0x1800566ae  mov     rcx, rdi
0x1800566b1  call    dwCalcMaxKeywordSize
0x1800566b6  mov     rcx, [rdi+420h]
0x1800566bd  mov     [rcx+10Ch], eax
0x1800566c3  call    cs:__imp_GetUserDefaultUILanguage
0x1800566c9  movzx   ecx, ax
0x1800566cc  mov     rdx, rsi
0x1800566cf  mov     rax, [rdi+428h]
0x1800566d6  mov     [rax+0DCh], ecx
0x1800566dc  mov     rcx, rdi
0x1800566df  call    BSaveBinaryDataToFile
0x1800566e4  mov     edx, [rdi+410h]; uBytes
0x1800566ea  xor     ecx, ecx; uFlags
0x1800566ec  call    cs:__imp_LocalAlloc
0x1800566f2  mov     rbx, rax
0x1800566f5  test    rax, rax
0x1800566f8  jz      short loc_180056710
0x1800566fa  mov     r8d, [rdi+410h]; Size
0x180056701  mov     rcx, rax; void *
0x180056704  mov     rdx, [rdi+400h]; Src
0x18005670b  call    memcpy_0
0x180056710  mov     rcx, rdi
0x180056713  call    VFreeParserData
0x180056718  mov     rax, rbx
0x18005671b  jmp     short loc_180056732
0x18005671d  mov     rcx, rdi
0x180056720  call    VFreeParserData
0x180056725  jmp     short loc_180056730
0x180056727  mov     rcx, rbx; hHeap
0x18005672a  call    cs:__imp_HeapDestroy
0x180056730  xor     eax, eax
0x180056732  add     rsp, 28h
0x180056736  pop     rdi
0x180056737  pop     rsi
0x180056738  pop     rbp
0x180056739  pop     rbx
0x18005673a  retn
```
