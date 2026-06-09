# ScCacheGetOrAddCardState

- ea: `0x180022a88`
- end: `0x180022c78`
- name: `ScCacheGetOrAddCardState`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180022c80`

## callees

- `0x18000de80`
- `0x180017bac`
- `0x180019650`
- `0x1800196ac`
- `0x180022a88`
- `0x18002835c`
- `0x18002896c`
- `0x180028c88`
- `0x18002bf00`
- `0x18002bf84`

## pseudocode

```c
__int64 __fastcall ScCacheGetOrAddCardState(
        __int64 a1,
        __int64 a2,
        struct _RTL_CRITICAL_SECTION *a3,
        char *a4,
        __int64 a5,
        _QWORD *a6)
{
  unsigned int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rdi
  unsigned int v12; // ebx
  __int64 v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // rcx
  int v17; // [rsp+20h] [rbp-48h]
  int v18; // [rsp+28h] [rbp-40h]
  __int64 v19; // [rsp+40h] [rbp-28h] BYREF
  __int64 v20; // [rsp+48h] [rbp-20h] BYREF
  __int64 Src; // [rsp+78h] [rbp+10h] BYREF

  Src = a2;
  v20 = 0;
  LODWORD(v19) = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids, WPP_pszIndent);
  }
  CspEnterCriticalSection(a1);
  v9 = ScCacheRead(a3, (__int64)a4, 0, a5, v17, v18, &v20, &v19);
  v11 = v20;
  v12 = v9;
  if ( v9 )
  {
    if ( v9 + 2146434960 <= 1 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(Src + 692));
      v14 = ScCacheWrite(a3, a4, 0, a5, 0, 0, &Src, 8u);
      if ( v14 )
        v12 = v14;
    }
  }
  else if ( (_DWORD)v19 == 8 )
  {
    v13 = *(_QWORD *)v20;
    *a6 = *(_QWORD *)v20;
    _InterlockedIncrement((volatile signed __int32 *)(v13 + 692));
  }
  else
  {
    WppTraceIndent(v10, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids, WPP_pszIndent);
    }
    ScCacheDeleteItem(a3);
    v12 = -2146435041;
  }
  if ( v11 )
    CspFreeH(v11);
  CspLeaveCriticalSection(a1);
  WppTraceIndent(v15, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
      (_DWORD)WPP_pszIndent,
      v12);
  }
  return v12;
}

```

## disassembly

```asm
0x180022a88  mov     rax, rsp
0x180022a8b  mov     [rax+8], rbx
0x180022a8f  mov     [rax+18h], rbp
0x180022a93  mov     [rax+10h], rdx
0x180022a97  push    rsi
0x180022a98  push    rdi
0x180022a99  push    r15
0x180022a9b  sub     rsp, 50h
0x180022a9f  xor     edx, edx
0x180022aa1  mov     qword ptr [rax-20h], 0
0x180022aa9  mov     rsi, r9
0x180022aac  mov     dword ptr [rax-28h], 0
0x180022ab3  mov     rbp, r8
0x180022ab6  mov     r15, rcx
0x180022ab9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180022abe  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ac5  lea     rax, WPP_GLOBAL_Control
0x180022acc  cmp     rcx, rax
0x180022acf  jz      short loc_180022AF9
0x180022ad1  test    byte ptr [rcx+1Ch], 2
0x180022ad5  jz      short loc_180022AF9
0x180022ad7  cmp     byte ptr [rcx+19h], 5
0x180022adb  jb      short loc_180022AF9
0x180022add  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180022ae4  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180022aeb  mov     rcx, [rcx+10h]
0x180022aef  mov     edx, 1Eh
0x180022af4  call    WPP_SF_s
0x180022af9  mov     rcx, r15
0x180022afc  call    CspEnterCriticalSection
0x180022b01  mov     r9, [rsp+68h+arg_20]
0x180022b09  lea     rax, [rsp+68h+var_28]
0x180022b0e  mov     [rsp+68h+var_30], rax; __int64
0x180022b13  xor     r8d, r8d
0x180022b16  lea     rax, [rsp+68h+var_20]
0x180022b1b  mov     rdx, rsi
0x180022b1e  mov     rcx, rbp; lpCriticalSection
0x180022b21  mov     [rsp+68h+Src], rax; __int64
0x180022b26  call    ScCacheRead
0x180022b2b  mov     rdi, [rsp+68h+var_20]
0x180022b30  mov     ebx, eax
0x180022b32  test    eax, eax
0x180022b34  jnz     short loc_180022BAF
0x180022b36  cmp     dword ptr [rsp+68h+var_28], 8
0x180022b3b  jz      short loc_180022B98
0x180022b3d  lea     edx, [rax+2]
0x180022b40  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180022b45  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b4c  lea     rax, WPP_GLOBAL_Control
0x180022b53  cmp     rcx, rax
0x180022b56  jz      short loc_180022B7E
0x180022b58  test    byte ptr [rcx+1Ch], 1
0x180022b5c  jz      short loc_180022B7E
0x180022b5e  cmp     byte ptr [rcx+19h], 2
0x180022b62  jb      short loc_180022B7E
0x180022b64  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180022b6b  lea     edx, [rbx+1Fh]
0x180022b6e  mov     rcx, [rcx+10h]
0x180022b72  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180022b79  call    WPP_SF_s
0x180022b7e  mov     r8, [rsp+68h+arg_20]
0x180022b86  mov     rdx, rsi
0x180022b89  mov     rcx, rbp; lpCriticalSection
0x180022b8c  call    ScCacheDeleteItem
0x180022b91  mov     ebx, 8010001Fh
0x180022b96  jmp     short loc_180022C03
0x180022b98  mov     rax, [rsp+68h+arg_28]
0x180022ba0  mov     rcx, [rdi]
0x180022ba3  mov     [rax], rcx
0x180022ba6  lock inc dword ptr [rcx+2B4h]
0x180022bad  jmp     short loc_180022C03
0x180022baf  add     eax, 7FEFFF90h
0x180022bb4  cmp     eax, 1
0x180022bb7  ja      short loc_180022C03
0x180022bb9  mov     rax, [rsp+68h+arg_8]
0x180022bbe  lock inc dword ptr [rax+2B4h]
0x180022bc5  mov     r9, [rsp+68h+arg_20]
0x180022bcd  lea     rax, [rsp+68h+arg_8]
0x180022bd2  mov     dword ptr [rsp+68h+var_30], 8; int
0x180022bda  xor     r8d, r8d
0x180022bdd  mov     [rsp+68h+Src], rax; Src
0x180022be2  mov     rdx, rsi
0x180022be5  mov     qword ptr [rsp+68h+var_40], 0; int
0x180022bee  mov     rcx, rbp; lpCriticalSection
0x180022bf1  mov     [rsp+68h+var_48], 0; int
0x180022bf9  call    ScCacheWrite
0x180022bfe  test    eax, eax
0x180022c00  cmovnz  ebx, eax
0x180022c03  test    rdi, rdi
0x180022c06  jz      short loc_180022C10
0x180022c08  mov     rcx, rdi
0x180022c0b  call    CspFreeH
0x180022c10  mov     rcx, r15
0x180022c13  call    CspLeaveCriticalSection
0x180022c18  mov     edx, 1
0x180022c1d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180022c22  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c29  lea     rax, WPP_GLOBAL_Control
0x180022c30  cmp     rcx, rax
0x180022c33  jz      short loc_180022C61
0x180022c35  test    byte ptr [rcx+1Ch], 2
0x180022c39  jz      short loc_180022C61
0x180022c3b  cmp     byte ptr [rcx+19h], 5
0x180022c3f  jb      short loc_180022C61
0x180022c41  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180022c48  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180022c4f  mov     rcx, [rcx+10h]
0x180022c53  mov     edx, 20h ; ' '
0x180022c58  mov     [rsp+68h+var_48], ebx
0x180022c5c  call    WPP_SF_sD
0x180022c61  lea     r11, [rsp+68h+var_18]
0x180022c66  mov     eax, ebx
0x180022c68  mov     rbx, [r11+20h]
0x180022c6c  mov     rbp, [r11+30h]
0x180022c70  mov     rsp, r11
0x180022c73  pop     r15
0x180022c75  pop     rdi
0x180022c76  pop     rsi
0x180022c77  retn
```
