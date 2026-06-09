# CopyPath(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,PATH_TYPE,bool,ushort const *)

- ea: `0x180020c30`
- end: `0x180020dfc`
- name: `?CopyPath@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@W4PATH_TYPE@@_NPEBG@Z`
- size: `460`
- prototype: `__int64 __fastcall(__int64, __int64, int, char, wchar_t *Source)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x18001ad40`
- `0x18001aec0`
- `0x18001b160`
- `0x18001b430`
- `0x180022684`

## callees

- `0x1800152d4`
- `0x18001c968`
- `0x18001f218`
- `0x180020c30`

## pseudocode

```c
__int64 __fastcall CopyPath(__int64 a1, __int64 a2, int a3, char a4, wchar_t *Source)
{
  const unsigned __int16 *v8; // rbp
  __int64 result; // rax
  int v10; // r14d
  __int16 v11; // ax
  __int64 v12; // r11
  unsigned __int16 v13; // si
  int v14; // ecx
  __int64 v15; // rdx
  unsigned int v16; // ecx
  __int64 v17; // r10
  __int64 v18; // rax
  unsigned __int16 *v19; // r12
  int v20; // eax
  __int64 v21; // r11
  unsigned int v22; // ebp
  __int16 v23; // cx
  unsigned __int16 v24; // cx
  __int64 v25; // r10
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // r11
  unsigned int v29; // esi
  int v30; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( a3 == 2 )
  {
    v8 = Source;
    if ( !Source )
      return 2147549183LL;
    LOWORD(v10) = 0;
    v11 = wcsnlen_s(Source, 0x4000u);
    v12 = 712;
    v13 = 2 * v11;
    goto LABEL_10;
  }
  if ( a4 )
  {
    v8 = *(const unsigned __int16 **)(a2 + 64);
    v13 = *(_WORD *)(a2 + 56);
  }
  else
  {
    v8 = *(const unsigned __int16 **)(a2 + 48);
    v13 = *(_WORD *)(a2 + 40);
  }
  v10 = *(unsigned __int16 *)(a1 + 60);
  if ( a3 )
  {
    v12 = 96;
LABEL_10:
    v14 = v13;
    goto LABEL_12;
  }
  v12 = 128;
  v14 = v10 + v13;
LABEL_12:
  v15 = *(unsigned __int16 *)(v12 + a2 + 2);
  v16 = v14 + 6;
  if ( v16 > (unsigned int)v15 )
    return 2147942511LL;
  if ( v16 + *(unsigned __int16 *)(v12 + a2) > (unsigned int)v15 )
    return 2147942522LL;
  v17 = *(unsigned __int16 *)(v12 + a2);
  v18 = 0;
  v19 = (unsigned __int16 *)(v17 + *(_QWORD *)(v12 + a2 + 8) + 2);
  if ( !(_WORD)v17 )
    v19 = (unsigned __int16 *)(v17 + *(_QWORD *)(v12 + a2 + 8));
  LOBYTE(v18) = (_WORD)v17 != 0;
  v20 = StringCchCopyNW(v19, ((unsigned __int64)(v15 - v17) >> 1) - v18, v8, (unsigned __int64)v13 >> 1);
  v22 = v20;
  if ( v20 >= 0 )
  {
    v23 = *(_WORD *)(v21 + a2);
    if ( v23 )
    {
      *(v19 - 1) = 124;
      v23 = *(_WORD *)(v21 + a2) + 2;
    }
    v24 = v13 + v23;
    result = 0;
    *(_WORD *)(v21 + a2) = v24;
    if ( !a3 && (_WORD)v10 )
    {
      v25 = v24;
      v26 = *(_QWORD *)(v21 + a2 + 8);
      *(_WORD *)(v25 + v26) = 92;
      *(_WORD *)(v21 + a2) += 2;
      v27 = StringCchCopyNW(
              (unsigned __int16 *)(v25 + 2 + v26),
              (*(unsigned __int16 *)(v21 + a2 + 2) - (unsigned __int64)*(unsigned __int16 *)(v21 + a2)) >> 1,
              (const unsigned __int16 *)(a1 + 88),
              (unsigned __int64)(unsigned __int16)v10 >> 1);
      v29 = v27;
      if ( v27 >= 0 )
      {
        *(_WORD *)(v28 + a2) += v10;
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x333,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\dirscanner.cpp",
          (const char *)(unsigned int)v27,
          v30);
        return v29;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x317,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\dirscanner.cpp",
      (const char *)(unsigned int)v20,
      v30);
    return v22;
  }
  return result;
}

```

## disassembly

```asm
0x180020c30  push    rbx
0x180020c32  push    rbp
0x180020c33  push    rsi
0x180020c34  push    rdi
0x180020c35  push    r12
0x180020c37  push    r13
0x180020c39  push    r14
0x180020c3b  push    r15
0x180020c3d  sub     rsp, 28h
0x180020c41  xor     edi, edi
0x180020c43  mov     r15d, r8d
0x180020c46  mov     rbx, rdx
0x180020c49  mov     r13, rcx
0x180020c4c  cmp     r8d, 2
0x180020c50  jnz     short loc_180020C88
0x180020c52  mov     rbp, [rsp+68h+Source]
0x180020c5a  test    rbp, rbp
0x180020c5d  jnz     short loc_180020C69
0x180020c5f  mov     eax, 8000FFFFh
0x180020c64  jmp     loc_180020DEB
0x180020c69  mov     edx, 4000h; MaxCount
0x180020c6e  mov     rcx, rbp; Source
0x180020c71  movzx   r14d, di
0x180020c75  call    wcsnlen_s
0x180020c7a  mov     rsi, rax
0x180020c7d  mov     r11d, 2C8h
0x180020c83  add     si, si
0x180020c86  jmp     short loc_180020CAF
0x180020c88  test    r9b, r9b
0x180020c8b  jz      short loc_180020C97
0x180020c8d  mov     rbp, [rdx+40h]
0x180020c91  movzx   esi, word ptr [rdx+38h]
0x180020c95  jmp     short loc_180020C9F
0x180020c97  mov     rbp, [rdx+30h]
0x180020c9b  movzx   esi, word ptr [rdx+28h]
0x180020c9f  movzx   r14d, word ptr [rcx+3Ch]
0x180020ca4  test    r15d, r15d
0x180020ca7  jz      short loc_180020CB4
0x180020ca9  mov     r11d, 60h ; '`'
0x180020caf  movzx   ecx, si
0x180020cb2  jmp     short loc_180020CC0
0x180020cb4  movzx   ecx, si
0x180020cb7  mov     r11d, 80h
0x180020cbd  add     ecx, r14d
0x180020cc0  movzx   edx, word ptr [r11+rbx+2]
0x180020cc6  add     ecx, 6
0x180020cc9  cmp     ecx, edx
0x180020ccb  jbe     short loc_180020CD7
0x180020ccd  mov     eax, 8007006Fh
0x180020cd2  jmp     loc_180020DEB
0x180020cd7  movzx   eax, word ptr [r11+rbx]
0x180020cdc  add     eax, ecx
0x180020cde  cmp     eax, edx
0x180020ce0  jbe     short loc_180020CEC
0x180020ce2  mov     eax, 8007007Ah
0x180020ce7  jmp     loc_180020DEB
0x180020cec  movzx   r10d, word ptr [r11+rbx]
0x180020cf1  mov     rax, rdi
0x180020cf4  mov     rcx, [r11+rbx+8]
0x180020cf9  mov     r8, rbp; unsigned __int16 *
0x180020cfc  add     rcx, r10
0x180020cff  movzx   r9d, si
0x180020d03  test    r10w, r10w
0x180020d07  lea     r12, [rcx+2]
0x180020d0b  cmovz   r12, rcx
0x180020d0f  sub     rdx, r10
0x180020d12  shr     rdx, 1
0x180020d15  mov     rcx, r12; unsigned __int16 *
0x180020d18  shr     r9, 1; unsigned __int64
0x180020d1b  test    r10w, r10w
0x180020d1f  setnz   al
0x180020d22  sub     rdx, rax; unsigned __int64
0x180020d25  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180020d2a  mov     ebp, eax
0x180020d2c  test    eax, eax
0x180020d2e  jns     short loc_180020D50
0x180020d30  mov     rcx, [rsp+68h]; this
0x180020d35  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180020d3c  mov     r9d, eax; char *
0x180020d3f  mov     edx, 317h; void *
0x180020d44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020d49  mov     eax, ebp
0x180020d4b  jmp     loc_180020DEB
0x180020d50  movzx   ecx, word ptr [r11+rbx]
0x180020d55  mov     edx, 2
0x180020d5a  test    cx, cx
0x180020d5d  jz      short loc_180020D6F
0x180020d5f  mov     word ptr [r12-2], 7Ch ; '|'
0x180020d67  movzx   ecx, word ptr [r11+rbx]
0x180020d6c  add     cx, dx
0x180020d6f  add     cx, si
0x180020d72  mov     eax, edi
0x180020d74  mov     [r11+rbx], cx
0x180020d79  test    r15d, r15d
0x180020d7c  jnz     short loc_180020DEB
0x180020d7e  cmp     di, r14w
0x180020d82  jnb     short loc_180020DEB
0x180020d84  movzx   r10d, cx
0x180020d88  lea     r8, [r13+58h]; unsigned __int16 *
0x180020d8c  mov     rcx, [r11+rbx+8]
0x180020d91  movzx   r9d, r14w
0x180020d95  shr     r9, 1; unsigned __int64
0x180020d98  mov     word ptr [r10+rcx], 5Ch ; '\'
0x180020d9f  add     r10, 2
0x180020da3  add     [r11+rbx], dx
0x180020da8  add     rcx, r10; unsigned __int16 *
0x180020dab  movzx   eax, word ptr [r11+rbx]
0x180020db0  movzx   edx, word ptr [r11+rbx+2]
0x180020db6  sub     rdx, rax
0x180020db9  shr     rdx, 1; unsigned __int64
0x180020dbc  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180020dc1  mov     esi, eax
0x180020dc3  test    eax, eax
0x180020dc5  jns     short loc_180020DE4
0x180020dc7  mov     rcx, [rsp+68h]; this
0x180020dcc  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180020dd3  mov     r9d, eax; char *
0x180020dd6  mov     edx, 333h; void *
0x180020ddb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020de0  mov     eax, esi
0x180020de2  jmp     short loc_180020DEB
0x180020de4  add     [r11+rbx], r14w
0x180020de9  mov     eax, edi
0x180020deb  add     rsp, 28h
0x180020def  pop     r15
0x180020df1  pop     r14
0x180020df3  pop     r13
0x180020df5  pop     r12
0x180020df7  pop     rdi
0x180020df8  pop     rsi
0x180020df9  pop     rbp
0x180020dfa  pop     rbx
0x180020dfb  retn
```
