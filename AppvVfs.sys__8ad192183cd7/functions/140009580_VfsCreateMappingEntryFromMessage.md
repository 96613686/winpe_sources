# VfsCreateMappingEntryFromMessage

- ea: `0x140009580`
- end: `0x14000977c`
- name: `VfsCreateMappingEntryFromMessage`
- size: `508`
- prototype: `__int64 __fastcall(__int64, unsigned int, _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009784`

## callees

- `0x14000874c`
- `0x140009580`

## pseudocode

```c
__int64 __fastcall VfsCreateMappingEntryFromMessage(__int64 a1, unsigned int a2, _DWORD *a3, __int64 *a4)
{
  unsigned int v6; // eax
  __int64 v7; // rdi
  unsigned int v8; // ecx
  int v9; // r9d
  __int64 v10; // rsi
  int v11; // r11d
  __int64 v12; // r15
  int v13; // ebx
  int v14; // r14d
  int v15; // r12d
  __int64 v16; // r8
  int v17; // edx
  __int16 v18; // cx
  __int64 result; // rax
  int v20; // [rsp+40h] [rbp-49h]
  __int64 v21; // [rsp+48h] [rbp-41h] BYREF
  __int128 v22; // [rsp+50h] [rbp-39h] BYREF
  __int64 v23[2]; // [rsp+60h] [rbp-29h] BYREF
  __int128 v24; // [rsp+70h] [rbp-19h]
  __int128 v25; // [rsp+80h] [rbp-9h]
  __int128 v26; // [rsp+90h] [rbp+7h]
  UNICODE_STRING VolumeName; // [rsp+A0h] [rbp+17h] BYREF
  int v28; // [rsp+F0h] [rbp+67h]

  VolumeName = 0;
  v21 = 0;
  v6 = *(_DWORD *)a1;
  v26 = 0;
  v25 = 0;
  v24 = 0;
  *(_OWORD *)v23 = 0;
  v22 = 0;
  if ( v6 )
  {
    if ( a2 < v6 )
      return 3221225485LL;
    a2 = v6;
  }
  if ( a2 < 0x2C )
    return 3221225485LL;
  v7 = *(unsigned __int16 *)(a1 + 8);
  v8 = a2 - 40;
  v9 = *(unsigned __int16 *)(a1 + 16);
  if ( (int)v7 + v9 > a2 - 40 )
    return 3221225485LL;
  v10 = *(unsigned __int16 *)(a1 + 10);
  v11 = *(unsigned __int16 *)(a1 + 18);
  if ( (int)v10 + v11 > v8 )
    return 3221225485LL;
  v12 = *(unsigned __int16 *)(a1 + 12);
  v13 = *(unsigned __int16 *)(a1 + 20);
  if ( (int)v12 + v13 > v8 )
    return 3221225485LL;
  v14 = *(unsigned __int16 *)(a1 + 32);
  v28 = *(unsigned __int16 *)(a1 + 24);
  if ( v28 + v14 > v8 )
    return 3221225485LL;
  v15 = *(unsigned __int16 *)(a1 + 34);
  v20 = *(unsigned __int16 *)(a1 + 26);
  if ( v20 + v15 > v8 )
    return 3221225485LL;
  v16 = *(unsigned __int16 *)(a1 + 28);
  v17 = *(unsigned __int16 *)(a1 + 36);
  if ( (int)v16 + v17 > v8 )
    return 3221225485LL;
  LOWORD(v25) = *(_WORD *)(a1 + 20);
  WORD1(v25) = v13;
  VolumeName.Buffer = (wchar_t *)(v7 + a1 + 40);
  VolumeName.Length = v9;
  VolumeName.MaximumLength = v9;
  *((_QWORD *)&v26 + 1) = v10 + a1 + 40;
  LOWORD(v26) = v11;
  *((_QWORD *)&v25 + 1) = v12 + a1 + 40;
  WORD1(v26) = v11;
  LOWORD(v24) = v14;
  *((_QWORD *)&v24 + 1) = a1 + (unsigned __int16)v28 + 40LL;
  WORD1(v24) = v14;
  LOWORD(v23[0]) = v15;
  v23[1] = a1 + (unsigned __int16)v20 + 40LL;
  v18 = 0;
  WORD1(v23[0]) = v15;
  LOWORD(v22) = 0;
  if ( (_WORD)v17 )
  {
    LOWORD(v22) = v17;
    WORD1(v22) = v17;
    *((_QWORD *)&v22 + 1) = v16 + a1 + 40;
    v18 = v17;
  }
  *a3 = *(_DWORD *)(a1 + 4);
  result = VfsCreateMappingEntry(
             &VolumeName,
             (__int64)v23,
             (unsigned __int64)&v22 & -(__int64)(v18 != 0),
             (__int64)a3,
             (__int64)&v21);
  if ( (int)result >= 0 )
    *a4 = v21;
  return result;
}

```

## disassembly

```asm
0x140009580  mov     [rsp-8+arg_8], rbx
0x140009585  mov     [rsp-8+arg_18], r9
0x14000958a  push    rbp
0x14000958b  push    rsi
0x14000958c  push    rdi
0x14000958d  push    r12
0x14000958f  push    r13
0x140009591  push    r14
0x140009593  push    r15
0x140009595  lea     rbp, [rsp-27h]
0x14000959a  sub     rsp, 0B0h
0x1400095a1  xorps   xmm0, xmm0
0x1400095a4  xorps   xmm1, xmm1
0x1400095a7  mov     r10, rcx
0x1400095aa  mov     r13, r8
0x1400095ad  xor     ecx, ecx
0x1400095af  movups  xmmword ptr [rbp+57h+VolumeName.Length], xmm0
0x1400095b3  mov     [rbp+57h+var_98], rcx
0x1400095b7  mov     eax, [r10]
0x1400095ba  movups  [rbp+57h+var_50], xmm1
0x1400095be  movups  [rbp+57h+var_60], xmm0
0x1400095c2  movups  [rbp+57h+var_70], xmm1
0x1400095c6  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x1400095ca  movups  [rbp+57h+var_90], xmm1
0x1400095ce  test    eax, eax
0x1400095d0  jz      short loc_1400095DC
0x1400095d2  cmp     edx, eax
0x1400095d4  jb      loc_14000975B
0x1400095da  mov     edx, eax
0x1400095dc  cmp     edx, 2Ch ; ','
0x1400095df  jb      loc_14000975B
0x1400095e5  movzx   edi, word ptr [r10+8]
0x1400095ea  lea     ecx, [rdx-28h]
0x1400095ed  movzx   r9d, word ptr [r10+10h]
0x1400095f2  lea     eax, [rdi+r9]
0x1400095f6  cmp     eax, ecx
0x1400095f8  ja      loc_14000975B
0x1400095fe  movzx   esi, word ptr [r10+0Ah]
0x140009603  movzx   r11d, word ptr [r10+12h]
0x140009608  lea     eax, [rsi+r11]
0x14000960c  cmp     eax, ecx
0x14000960e  ja      loc_14000975B
0x140009614  movzx   r15d, word ptr [r10+0Ch]
0x140009619  movzx   ebx, word ptr [r10+14h]
0x14000961e  lea     eax, [r15+rbx]
0x140009622  cmp     eax, ecx
0x140009624  ja      loc_14000975B
0x14000962a  movzx   edx, word ptr [r10+18h]
0x14000962f  movzx   r14d, word ptr [r10+20h]
0x140009634  mov     [rbp+57h+arg_0], edx
0x140009637  lea     eax, [rdx+r14]
0x14000963b  cmp     eax, ecx
0x14000963d  ja      loc_14000975B
0x140009643  movzx   edx, word ptr [r10+1Ah]
0x140009648  movzx   r12d, word ptr [r10+22h]
0x14000964d  mov     [rbp+57h+var_A0], edx
0x140009650  lea     eax, [rdx+r12]
0x140009654  cmp     eax, ecx
0x140009656  ja      loc_14000975B
0x14000965c  movzx   r8d, word ptr [r10+1Ch]
0x140009661  movzx   edx, word ptr [r10+24h]
0x140009666  lea     eax, [r8+rdx]
0x14000966a  cmp     eax, ecx
0x14000966c  ja      loc_14000975B
0x140009672  lea     rcx, [r10+28h]
0x140009676  mov     word ptr [rbp+57h+var_60], bx
0x14000967a  add     rcx, rdi
0x14000967d  mov     word ptr [rbp+57h+var_60+2], bx
0x140009681  mov     [rbp+57h+VolumeName.Buffer], rcx
0x140009685  xor     ebx, ebx
0x140009687  lea     rcx, [r10+28h]
0x14000968b  mov     [rbp+57h+VolumeName.Length], r9w
0x140009690  add     rcx, rsi
0x140009693  mov     [rbp+57h+VolumeName.MaximumLength], r9w
0x140009698  mov     qword ptr [rbp+57h+var_50+8], rcx
0x14000969c  lea     rcx, [r10+28h]
0x1400096a0  add     rcx, r15
0x1400096a3  mov     word ptr [rbp+57h+var_50], r11w
0x1400096a8  mov     qword ptr [rbp+57h+var_60+8], rcx
0x1400096ac  movzx   ecx, word ptr [rbp+57h+arg_0]
0x1400096b0  add     rcx, 28h ; '('
0x1400096b4  mov     word ptr [rbp+57h+var_50+2], r11w
0x1400096b9  add     rcx, r10
0x1400096bc  mov     word ptr [rbp+57h+var_70], r14w
0x1400096c1  mov     qword ptr [rbp+57h+var_70+8], rcx
0x1400096c5  movzx   ecx, word ptr [rbp+57h+var_A0]
0x1400096c9  add     rcx, 28h ; '('
0x1400096cd  mov     word ptr [rbp+57h+var_70+2], r14w
0x1400096d2  add     rcx, r10
0x1400096d5  mov     word ptr [rbp+57h+var_80], r12w
0x1400096da  mov     [rbp+57h+var_80+8], rcx
0x1400096de  mov     ecx, ebx
0x1400096e0  mov     word ptr [rbp+57h+var_80+2], r12w
0x1400096e5  mov     word ptr [rbp+57h+var_90], bx
0x1400096e9  test    dx, dx
0x1400096ec  jz      short loc_140009704
0x1400096ee  lea     rcx, [r10+28h]
0x1400096f2  mov     word ptr [rbp+57h+var_90], dx
0x1400096f6  add     rcx, r8
0x1400096f9  mov     word ptr [rbp+57h+var_90+2], dx
0x1400096fd  mov     qword ptr [rbp+57h+var_90+8], rcx
0x140009701  movzx   ecx, dx
0x140009704  mov     eax, [r10+4]
0x140009708  lea     r9, [rbp+57h+var_70]
0x14000970c  neg     cx
0x14000970f  mov     [r13+0], eax
0x140009713  lea     rcx, [rbp+57h+var_90]
0x140009717  sbb     rax, rax
0x14000971a  lea     r8, [rbp+57h+var_60]
0x14000971e  and     rax, rcx
0x140009721  lea     rdx, [rbp+57h+var_50]
0x140009725  lea     rcx, [rbp+57h+var_98]
0x140009729  mov     [rsp+0E0h+var_A8], rcx; __int64
0x14000972e  lea     rcx, [rbp+57h+VolumeName]; VolumeName
0x140009732  mov     [rsp+0E0h+var_B0], r13; __int64
0x140009737  mov     [rsp+0E0h+var_B8], rax; __int64
0x14000973c  lea     rax, [rbp+57h+var_80]
0x140009740  mov     [rsp+0E0h+var_C0], rax; __int64
0x140009745  call    VfsCreateMappingEntry
0x14000974a  test    eax, eax
0x14000974c  js      short loc_140009760
0x14000974e  mov     rdx, [rbp+57h+arg_18]
0x140009752  mov     rcx, [rbp+57h+var_98]
0x140009756  mov     [rdx], rcx
0x140009759  jmp     short loc_140009760
0x14000975b  mov     eax, 0C000000Dh
0x140009760  mov     rbx, [rsp+0E0h+arg_8]
0x140009768  add     rsp, 0B0h
0x14000976f  pop     r15
0x140009771  pop     r14
0x140009773  pop     r13
0x140009775  pop     r12
0x140009777  pop     rdi
0x140009778  pop     rsi
0x140009779  pop     rbp
0x14000977a  retn
```
