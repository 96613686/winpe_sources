# std::basic_filebuf<ushort,std::char_traits<ushort>>::overflow(ushort)

- ea: `0x18003f4f0`
- end: `0x18003f681`
- name: `?overflow@?$basic_filebuf@GU?$char_traits@G@std@@@std@@MEAAGG@Z`
- size: `401`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18003f4f0`
- `0x180049b50`

## import_xrefs

- `MSVCP140!?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z` at `0x18003f602`
- `MSVCP140!?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z` at `0x18003f602`
- `api-ms-win-crt-stdio-l1-1-0!fputwc` at `0x18003f5bf`
- `api-ms-win-crt-stdio-l1-1-0!fputwc` at `0x18003f5bf`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x18003f63f`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x18003f63f`

## pseudocode

```c
__int64 __fastcall std::basic_filebuf<unsigned short>::overflow(__int64 a1, wchar_t a2)
{
  unsigned __int16 v2; // si
  wchar_t v3; // di
  unsigned __int64 v6; // r8
  int *v7; // rax
  __int64 v8; // r9
  _WORD **v9; // rdx
  wchar_t *v10; // r8
  _QWORD *v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  wchar_t v15; // cx
  int v16; // eax
  int v17; // eax
  __int64 v18; // r14
  _BYTE *v19; // [rsp+40h] [rbp-40h] BYREF
  wchar_t *v20; // [rsp+48h] [rbp-38h] BYREF
  wchar_t v21; // [rsp+50h] [rbp-30h] BYREF
  char v22[6]; // [rsp+52h] [rbp-2Eh] BYREF
  _BYTE Buffer[32]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v24; // [rsp+78h] [rbp-8h] BYREF

  v2 = -1;
  v3 = a2;
  if ( a2 == 0xFFFF )
    return 0;
  v6 = **(_QWORD **)(a1 + 64);
  if ( v6 )
  {
    v7 = *(int **)(a1 + 88);
    v8 = *v7;
    if ( v6 < v6 + 2 * v8 )
    {
      *v7 = v8 - 1;
      v9 = *(_WORD ***)(a1 + 64);
      v10 = (*v9)++;
      *v10 = v3;
      return v3;
    }
  }
  if ( *(_QWORD *)(a1 + 128) )
  {
    v11 = *(_QWORD **)(a1 + 24);
    if ( *v11 == a1 + 112 )
    {
      v12 = *(_QWORD *)(a1 + 144);
      v13 = *(_QWORD *)(a1 + 136);
      *v11 = v13;
      **(_QWORD **)(a1 + 56) = v13;
      **(_DWORD **)(a1 + 80) = (v12 - v13) >> 1;
    }
    v14 = *(_QWORD *)(a1 + 104);
    if ( !v14 )
    {
      v15 = v3;
      goto LABEL_12;
    }
    v21 = v3;
    v16 = std::codecvt<unsigned short,char,_Mbstatet>::out(v14, a1 + 116, &v21, v22, &v20, Buffer, &v24, &v19);
    if ( v16 && (v17 = v16 - 1) != 0 )
    {
      if ( v17 == 2 )
      {
        v15 = v21;
LABEL_12:
        if ( fputwc(v15, *(FILE **)(a1 + 128)) == 0xFFFF )
          return (wchar_t)-1;
        return v3;
      }
    }
    else if ( v19 == Buffer
           || (_mm_lfence(), v18 = v19 - Buffer, v18 == fwrite(Buffer, 1u, v19 - Buffer, *(FILE **)(a1 + 128))) )
    {
      *(_BYTE *)(a1 + 114) = 1;
      if ( v20 != &v21 )
        return v3;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18003f4f0  mov     [rsp-18h+arg_10], rbx
0x18003f4f5  mov     [rsp-18h+arg_18], rsi
0x18003f4fa  push    rbp
0x18003f4fb  push    rdi
0x18003f4fc  push    r14
0x18003f4fe  mov     rbp, rsp
0x18003f501  sub     rsp, 80h
0x18003f508  mov     rax, cs:__security_cookie
0x18003f50f  xor     rax, rsp
0x18003f512  mov     [rbp+var_8], rax
0x18003f516  mov     esi, 0FFFFh
0x18003f51b  xor     r14d, r14d
0x18003f51e  movzx   edi, dx
0x18003f521  mov     rbx, rcx
0x18003f524  cmp     dx, si
0x18003f527  jnz     short loc_18003F532
0x18003f529  movzx   eax, r14w
0x18003f52d  jmp     loc_18003F65D
0x18003f532  mov     rax, [rcx+40h]
0x18003f536  mov     r8, [rax]
0x18003f539  test    r8, r8
0x18003f53c  jz      short loc_18003F56E
0x18003f53e  mov     rax, [rcx+58h]
0x18003f542  movsxd  r9, dword ptr [rax]
0x18003f545  lea     rdx, [r8+r9*2]
0x18003f549  cmp     r8, rdx
0x18003f54c  jnb     short loc_18003F56E
0x18003f54e  lea     ecx, [r9-1]
0x18003f552  mov     [rax], ecx
0x18003f554  mov     rdx, [rbx+40h]
0x18003f558  mov     r8, [rdx]
0x18003f55b  lea     rcx, [r8+2]
0x18003f55f  mov     [rdx], rcx
0x18003f562  mov     [r8], di
0x18003f566  movzx   eax, di
0x18003f569  jmp     loc_18003F65D
0x18003f56e  cmp     [rcx+80h], r14
0x18003f575  jz      loc_18003F65A
0x18003f57b  mov     r8, [rcx+18h]
0x18003f57f  lea     rax, [rcx+70h]
0x18003f583  cmp     [r8], rax
0x18003f586  jnz     short loc_18003F5AC
0x18003f588  mov     rdx, [rcx+90h]
0x18003f58f  mov     rcx, [rcx+88h]
0x18003f596  mov     [r8], rcx
0x18003f599  sub     rdx, rcx
0x18003f59c  mov     rax, [rbx+38h]
0x18003f5a0  sar     rdx, 1
0x18003f5a3  mov     [rax], rcx
0x18003f5a6  mov     rax, [rbx+50h]
0x18003f5aa  mov     [rax], edx
0x18003f5ac  mov     rcx, [rbx+68h]
0x18003f5b0  test    rcx, rcx
0x18003f5b3  jnz     short loc_18003F5CE
0x18003f5b5  movzx   ecx, di; Character
0x18003f5b8  mov     rdx, [rbx+80h]; Stream
0x18003f5bf  call    cs:__imp_fputwc
0x18003f5c5  cmp     ax, si
0x18003f5c8  cmovz   di, si
0x18003f5cc  jmp     short loc_18003F566
0x18003f5ce  lea     rax, [rbp+var_40]
0x18003f5d2  mov     [rbp+var_30], di
0x18003f5d6  mov     [rsp+80h+var_48], rax
0x18003f5db  lea     rdx, [rbx+74h]
0x18003f5df  lea     rax, [rbp+var_8]
0x18003f5e3  mov     [rsp+80h+var_50], rax
0x18003f5e8  lea     r9, [rbp+var_2E]
0x18003f5ec  lea     rax, [rbp+Buffer]
0x18003f5f0  mov     [rsp+80h+var_58], rax
0x18003f5f5  lea     r8, [rbp+var_30]
0x18003f5f9  lea     rax, [rbp+var_38]
0x18003f5fd  mov     [rsp+80h+var_60], rax
0x18003f602  call    cs:__imp_?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z; std::codecvt<ushort,char,_Mbstatet>::out(_Mbstatet &,ushort const *,ushort const *,ushort const * &,char *,char *,char * &)
0x18003f608  test    eax, eax
0x18003f60a  jz      short loc_18003F61C
0x18003f60c  sub     eax, 1
0x18003f60f  jz      short loc_18003F61C
0x18003f611  cmp     eax, 2
0x18003f614  jnz     short loc_18003F65A
0x18003f616  movzx   ecx, [rbp+var_30]
0x18003f61a  jmp     short loc_18003F5B8
0x18003f61c  mov     r14, [rbp+var_40]
0x18003f620  lea     rax, [rbp+Buffer]
0x18003f624  sub     r14, rax
0x18003f627  jz      short loc_18003F64A
0x18003f629  lfence
0x18003f62c  mov     r9, [rbx+80h]; Stream
0x18003f633  lea     rcx, [rbp+Buffer]; Buffer
0x18003f637  mov     r8, r14; ElementCount
0x18003f63a  mov     edx, 1; ElementSize
0x18003f63f  call    cs:__imp_fwrite
0x18003f645  cmp     r14, rax
0x18003f648  jnz     short loc_18003F65A
0x18003f64a  lea     rax, [rbp+var_30]
0x18003f64e  mov     byte ptr [rbx+72h], 1
0x18003f652  cmp     [rbp+var_38], rax
0x18003f656  cmovnz  si, di
0x18003f65a  movzx   eax, si
0x18003f65d  mov     rcx, [rbp+var_8]
0x18003f661  xor     rcx, rsp; StackCookie
0x18003f664  call    __security_check_cookie
0x18003f669  lea     r11, [rsp+80h+var_s0]
0x18003f671  mov     rbx, [r11+30h]
0x18003f675  mov     rsi, [r11+38h]
0x18003f679  mov     rsp, r11
0x18003f67c  pop     r14
0x18003f67e  pop     rdi
0x18003f67f  pop     rbp
0x18003f680  retn
```
