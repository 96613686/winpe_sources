# CTxtRange::Update_iFormat(long)

- ea: `0x180017ef0`
- end: `0x180018383`
- name: `?Update_iFormat@CTxtRange@@QEAAXJ@Z`
- size: `1171`
- prototype: `void __fastcall(CTxtRange *__hidden this, int)`
- caller_count: `21`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180002044`
- `0x180005480`
- `0x18000dd60`
- `0x180016b44`
- `0x1800175d0`
- `0x180017860`
- `0x180018c9c`
- `0x180018ea8`
- `0x18001ebcc`
- `0x18002bfc0`
- `0x18002cfd0`
- `0x1800323d8`
- `0x180033060`
- `0x18003e0f0`
- `0x18003f9c0`
- `0x180044094`
- `0x18005e300`
- `0x18005e8f8`
- `0x180071d04`
- `0x180071d80`
- `0x180071e68`

## callees

- `0x180005480`
- `0x1800165c0`
- `0x180017ef0`
- `0x180092010`

## pseudocode

```c
void __fastcall CTxtRange::Update_iFormat(CTxtRange *this, int a2)
{
  int v2; // esi
  __int64 v4; // rcx
  __int64 *v5; // r12
  int v6; // r8d
  int v7; // edx
  _DWORD *v8; // r9
  int v9; // edx
  int v10; // eax
  __int64 v11; // rax
  unsigned int v12; // eax
  int v13; // r15d
  __int64 v14; // rdx
  char *v15; // rdi
  __int64 *v16; // r14
  int v17; // ebp
  __int64 v18; // rcx
  int v19; // eax
  int v20; // eax
  int v21; // edx
  _DWORD *v22; // rax
  __int64 v23; // rcx
  int v24; // edx
  int v25; // eax
  __int64 v26; // rax
  unsigned int v27; // eax
  __int64 v28; // rdx
  __int64 *v29; // rcx
  __int64 v30; // rdx
  __int128 v31; // xmm0
  __int64 v32; // xmm1_8
  int v33; // eax
  struct IFormatCache *v34; // rdi
  _OWORD v35[2]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v36; // [rsp+50h] [rbp-48h]
  __int64 *v37; // [rsp+A0h] [rbp+8h] BYREF
  __int64 *v38; // [rsp+B0h] [rbp+18h] BYREF

  v2 = a2;
  if ( !*((_DWORD *)this + 22) )
  {
    *((_WORD *)this + 49) &= 0xFE7Fu;
    if ( (*((_BYTE *)this + 98) & 8) == 0 )
    {
      v4 = *((_QWORD *)this + 7);
      v5 = g_defaultCF;
      if ( !v4 || (v6 = *(_DWORD *)(v4 + 8)) == 0 )
      {
        v15 = (char *)this + 48;
        goto LABEL_51;
      }
      if ( a2 != -1 )
      {
        v15 = (char *)this + 48;
        goto LABEL_60;
      }
      v7 = *((_DWORD *)this + 16);
      if ( v6 > 0 && v7 < v6 && *(_QWORD *)v4 && v7 >= 0 )
        v8 = (_DWORD *)(*(_QWORD *)v4 + *(_DWORD *)(v4 + 16) * v7);
      else
        v8 = 0;
      if ( *v8 == *((_DWORD *)this + 17) && v7 < v6 - 1 )
        *((_QWORD *)this + 8) = (unsigned int)(v7 + 1);
      v9 = *(_DWORD *)(v4 + 8);
      if ( v9 )
      {
        if ( v9 > 0 && (v10 = *((_DWORD *)this + 16), v10 < v9) && *(_QWORD *)v4 && v10 >= 0 )
          v11 = *(_QWORD *)v4 + *(_DWORD *)(v4 + 16) * v10;
        else
          v11 = 0;
        v12 = *(__int16 *)(v11 + 4);
        v37 = 0;
        v13 = v12;
        v14 = v12;
        if ( (v12 & 0x8000u) == 0 )
        {
          v15 = (char *)this + 48;
LABEL_23:
          if ( (*(int (__fastcall **)(struct IFormatCache *, __int64, __int64 **))(*(_QWORD *)qword_1800A41F0 + 32LL))(
                 qword_1800A41F0,
                 v14,
                 &v37) >= 0 )
          {
            v16 = v37;
          }
          else
          {
            v16 = g_defaultCF;
            v37 = g_defaultCF;
          }
          v17 = *(_DWORD *)v16;
          if ( (unsigned int)CTxtPtr::IsAfterEOP((CTxtRange *)((char *)this + 24)) )
          {
            v2 = v13;
            v29 = v16;
            goto LABEL_47;
          }
          if ( !*((_DWORD *)this + 17) )
          {
            v18 = *((_QWORD *)this + 7);
            if ( v18 )
            {
              v19 = *((_DWORD *)this + 16);
              *((_DWORD *)this + 17) = 0;
              if ( v19 > 0 )
              {
                v20 = v19 - 1;
                *((_DWORD *)this + 16) = v20;
                v21 = *(_DWORD *)(v18 + 8);
                if ( v21 > 0 && v20 < v21 && *(_QWORD *)v18 && v20 >= 0 )
                  v22 = (_DWORD *)(*(_QWORD *)v18 + *(_DWORD *)(v18 + 16) * v20);
                else
                  v22 = 0;
                *((_DWORD *)this + 17) = *v22;
              }
            }
          }
          v23 = *((_QWORD *)this + 7);
          if ( v23 && (v24 = *(_DWORD *)(v23 + 8)) != 0 )
          {
            if ( v24 > 0 && (v25 = *((_DWORD *)this + 16), v25 < v24) && *(_QWORD *)v23 && v25 >= 0 )
              v26 = *(_QWORD *)v23 + *(_DWORD *)(v23 + 16) * v25;
            else
              v26 = 0;
            v27 = *(__int16 *)(v26 + 4);
            v38 = 0;
            v2 = v27;
            v28 = v27;
            if ( (v27 & 0x8000u) == 0 )
            {
              v15 = (char *)this + 48;
              goto LABEL_44;
            }
          }
          else
          {
            v38 = 0;
            v2 = -1;
          }
          v15 = (char *)this + 48;
          v28 = (unsigned int)*(__int16 *)(*((_QWORD *)this + 6) + 276LL);
LABEL_44:
          if ( (*(int (__fastcall **)(struct IFormatCache *, __int64, __int64 **))(*(_QWORD *)qword_1800A41F0 + 32LL))(
                 qword_1800A41F0,
                 v28,
                 &v38) >= 0 )
          {
            v29 = v38;
          }
          else
          {
            v29 = g_defaultCF;
            v38 = g_defaultCF;
          }
          v17 = *(_DWORD *)v29;
LABEL_47:
          if ( (*(_WORD *)(*(_QWORD *)v15 + 184LL) & 0x4000) == 0 )
          {
            if ( *((_DWORD *)this + 10) || (*(_DWORD *)v29 & 0x40000) == 0 )
            {
              if ( (v17 & 0x40130) != 0 )
              {
                v2 = v13;
              }
              else if ( v2 != v13
                     && (*((_BYTE *)this + 98) & 0x40) != 0
                     && (unsigned int)*((unsigned __int8 *)v29 + 4) - 177 <= 1 != (unsigned int)*((unsigned __int8 *)v16
                                                                                                + 4)
                                                                                - 177 <= 1 )
              {
                v2 = v13;
              }
            }
            else
            {
              v2 = -1;
            }
          }
LABEL_51:
          if ( v2 == -1 )
          {
LABEL_52:
            if ( v2 != *((__int16 *)this + 48) )
            {
              v34 = qword_1800A41F0;
              (**(void (__fastcall ***)(struct IFormatCache *, _QWORD))qword_1800A41F0)(
                qword_1800A41F0,
                (unsigned int)v2);
              (*(void (__fastcall **)(struct IFormatCache *, _QWORD))(*(_QWORD *)v34 + 8LL))(
                v34,
                (unsigned int)*((__int16 *)this + 48));
              *((_WORD *)this + 48) = v2;
            }
            return;
          }
LABEL_60:
          v37 = 0;
          if ( v2 >= 0 )
            v30 = (unsigned int)v2;
          else
            v30 = (unsigned int)*(__int16 *)(*(_QWORD *)v15 + 276LL);
          if ( (*(int (__fastcall **)(struct IFormatCache *, __int64, __int64 **))(*(_QWORD *)qword_1800A41F0 + 32LL))(
                 qword_1800A41F0,
                 v30,
                 &v37) >= 0 )
            v5 = v37;
          else
            v37 = g_defaultCF;
          if ( (*(_DWORD *)v5 & 0x120) != 0 )
          {
            v31 = *((_OWORD *)v5 + 1);
            v32 = v5[4];
            v33 = _mm_cvtsi128_si32(*(__m128i *)v5);
            v35[0] = *(_OWORD *)v5;
            v36 = v32;
            LODWORD(v35[0]) = v33 & 0xFFFFFEDF;
            v35[1] = v31;
            CTxtRange::SetCharFormat(this, (const struct CCharFormat *)v35, 0, 0, 0xFEFFFFFF, 0);
            return;
          }
          goto LABEL_52;
        }
      }
      else
      {
        v37 = 0;
        v13 = -1;
      }
      v15 = (char *)this + 48;
      v14 = (unsigned int)*(__int16 *)(*((_QWORD *)this + 6) + 276LL);
      goto LABEL_23;
    }
  }
}

```

## disassembly

```asm
0x180017ef0  push    rbx
0x180017ef2  push    rsi
0x180017ef3  sub     rsp, 88h
0x180017efa  cmp     dword ptr [rcx+58h], 0
0x180017efe  mov     esi, edx
0x180017f00  mov     rbx, rcx
0x180017f03  jnz     short loc_180017F14
0x180017f05  mov     eax, 0FE7Fh
0x180017f0a  and     [rcx+62h], ax
0x180017f0e  test    byte ptr [rcx+62h], 8
0x180017f12  jz      short loc_180017F1E
0x180017f14  add     rsp, 88h
0x180017f1b  pop     rsi
0x180017f1c  pop     rbx
0x180017f1d  retn
0x180017f1e  mov     rcx, [rcx+38h]
0x180017f22  mov     [rsp+98h+var_20], r12
0x180017f27  lea     r12, ?g_defaultCF@@3VCCharFormat@@A; CCharFormat g_defaultCF
0x180017f2e  mov     [rsp+98h+var_28], r13
0x180017f33  xor     r13d, r13d
0x180017f36  mov     [rsp+98h+var_18], rdi
0x180017f3e  test    rcx, rcx
0x180017f41  jz      loc_1800181D8
0x180017f47  mov     r8d, [rcx+8]
0x180017f4b  test    r8d, r8d
0x180017f4e  jz      loc_1800181D8
0x180017f54  cmp     edx, 0FFFFFFFFh
0x180017f57  jnz     loc_1800181F0
0x180017f5d  mov     edx, [rbx+40h]
0x180017f60  mov     [rsp+98h+arg_8], rbp
0x180017f68  mov     [rsp+98h+var_30], r14
0x180017f6d  test    r8d, r8d
0x180017f70  jle     loc_180018303
0x180017f76  cmp     edx, r8d
0x180017f79  jge     loc_180018303
0x180017f7f  mov     r10, [rcx]
0x180017f82  test    r10, r10
0x180017f85  jz      loc_180018303
0x180017f8b  test    edx, edx
0x180017f8d  js      loc_180018303
0x180017f93  mov     eax, edx
0x180017f95  imul    eax, [rcx+10h]
0x180017f99  movsxd  r9, eax
0x180017f9c  add     r9, r10
0x180017f9f  mov     eax, [rbx+44h]
0x180017fa2  cmp     [r9], eax
0x180017fa5  jnz     short loc_180017FB9
0x180017fa7  lea     eax, [r8-1]
0x180017fab  cmp     edx, eax
0x180017fad  jge     short loc_180017FB9
0x180017faf  lea     eax, [rdx+1]
0x180017fb2  mov     [rbx+44h], r13d
0x180017fb6  mov     [rbx+40h], eax
0x180017fb9  mov     edx, [rcx+8]
0x180017fbc  mov     [rsp+98h+var_38], r15
0x180017fc1  test    edx, edx
0x180017fc3  jz      loc_18001832E
0x180017fc9  jle     loc_18001830B
0x180017fcf  mov     eax, [rbx+40h]
0x180017fd2  cmp     eax, edx
0x180017fd4  jge     loc_18001830B
0x180017fda  mov     rdx, [rcx]
0x180017fdd  test    rdx, rdx
0x180017fe0  jz      loc_18001830B
0x180017fe6  test    eax, eax
0x180017fe8  js      loc_18001830B
0x180017fee  imul    eax, [rcx+10h]
0x180017ff2  cdqe
0x180017ff4  add     rax, rdx
0x180017ff7  movsx   eax, word ptr [rax+4]
0x180017ffb  mov     [rsp+98h+arg_0], r13
0x180018003  mov     r15d, eax
0x180018006  mov     edx, eax
0x180018008  test    ax, ax
0x18001800b  jns     loc_1800182EA
0x180018011  mov     rax, [rbx+30h]
0x180018015  lea     rdi, [rbx+30h]
0x180018019  movsx   edx, word ptr [rax+114h]
0x180018020  mov     rcx, cs:qword_1800A41F0
0x180018027  lea     r8, [rsp+98h+arg_0]
0x18001802f  mov     rax, [rcx]
0x180018032  mov     rax, [rax+20h]
0x180018036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001803b  test    eax, eax
0x18001803d  jns     loc_1800181BE
0x180018043  mov     r14, r12
0x180018046  mov     [rsp+98h+arg_0], r12
0x18001804e  mov     ebp, [r14]
0x180018051  lea     rcx, [rbx+18h]; this
0x180018055  call    ?IsAfterEOP@CTxtPtr@@QEAAHXZ; CTxtPtr::IsAfterEOP(void)
0x18001805a  test    eax, eax
0x18001805c  jnz     loc_180018323
0x180018062  cmp     [rbx+44h], r13d
0x180018066  jnz     short loc_1800180B6
0x180018068  mov     rcx, [rbx+38h]
0x18001806c  test    rcx, rcx
0x18001806f  jz      short loc_1800180B6
0x180018071  mov     eax, [rbx+40h]
0x180018074  mov     [rbx+44h], r13d
0x180018078  test    eax, eax
0x18001807a  jle     short loc_1800180B6
0x18001807c  dec     eax
0x18001807e  mov     [rbx+40h], eax
0x180018081  mov     edx, [rcx+8]
0x180018084  test    edx, edx
0x180018086  jle     loc_18001831B
0x18001808c  cmp     eax, edx
0x18001808e  jge     loc_18001831B
0x180018094  mov     rdx, [rcx]
0x180018097  test    rdx, rdx
0x18001809a  jz      loc_18001831B
0x1800180a0  test    eax, eax
0x1800180a2  js      loc_18001831B
0x1800180a8  imul    eax, [rcx+10h]
0x1800180ac  cdqe
0x1800180ae  add     rax, rdx
0x1800180b1  mov     eax, [rax]
0x1800180b3  mov     [rbx+44h], eax
0x1800180b6  mov     rcx, [rbx+38h]
0x1800180ba  test    rcx, rcx
0x1800180bd  jz      loc_1800181DE
0x1800180c3  mov     edx, [rcx+8]
0x1800180c6  test    edx, edx
0x1800180c8  jz      loc_1800181DE
0x1800180ce  jle     loc_180018313
0x1800180d4  mov     eax, [rbx+40h]
0x1800180d7  cmp     eax, edx
0x1800180d9  jge     loc_180018313
0x1800180df  mov     rdx, [rcx]
0x1800180e2  test    rdx, rdx
0x1800180e5  jz      loc_180018313
0x1800180eb  test    eax, eax
0x1800180ed  js      loc_180018313
0x1800180f3  imul    eax, [rcx+10h]
0x1800180f7  cdqe
0x1800180f9  add     rax, rdx
0x1800180fc  movsx   eax, word ptr [rax+4]
0x180018100  mov     [rsp+98h+arg_10], r13
0x180018108  mov     esi, eax
0x18001810a  mov     edx, eax
0x18001810c  test    ax, ax
0x18001810f  jns     loc_1800182F3
0x180018115  mov     rax, [rbx+30h]
0x180018119  lea     rdi, [rbx+30h]
0x18001811d  movsx   edx, word ptr [rax+114h]
0x180018124  mov     rcx, cs:qword_1800A41F0
0x18001812b  lea     r8, [rsp+98h+arg_10]
0x180018133  mov     rax, [rcx]
0x180018136  mov     rax, [rax+20h]
0x18001813a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001813f  test    eax, eax
0x180018141  jns     loc_1800181CB
0x180018147  mov     rcx, r12
0x18001814a  mov     [rsp+98h+arg_10], rcx
0x180018152  mov     ebp, [rcx]
0x180018154  mov     rax, [rdi]
0x180018157  mov     edx, 4000h
0x18001815c  test    [rax+0B8h], dx
0x180018163  jnz     short loc_180018184
0x180018165  cmp     [rbx+28h], r13d
0x180018169  jz      loc_1800182D4
0x18001816f  test    ebp, 40130h
0x180018175  jnz     loc_180018341
0x18001817b  cmp     esi, r15d
0x18001817e  jnz     loc_180018349
0x180018184  mov     r15, [rsp+98h+var_38]
0x180018189  mov     r14, [rsp+98h+var_30]
0x18001818e  mov     rbp, [rsp+98h+arg_8]
0x180018196  cmp     esi, 0FFFFFFFFh
0x180018199  jnz     short loc_1800181F4
0x18001819b  movsx   eax, word ptr [rbx+60h]
0x18001819f  cmp     esi, eax
0x1800181a1  jnz     loc_1800182A1
0x1800181a7  mov     rdi, [rsp+98h+var_18]
0x1800181af  mov     r12, [rsp+98h+var_20]
0x1800181b4  mov     r13, [rsp+98h+var_28]
0x1800181b9  jmp     loc_180017F14
0x1800181be  mov     r14, [rsp+98h+arg_0]
0x1800181c6  jmp     loc_18001804E
0x1800181cb  mov     rcx, [rsp+98h+arg_10]
0x1800181d3  jmp     loc_180018152
0x1800181d8  lea     rdi, [rbx+30h]
0x1800181dc  jmp     short loc_180018196
0x1800181de  mov     [rsp+98h+arg_10], r13
0x1800181e6  mov     esi, 0FFFFFFFFh
0x1800181eb  jmp     loc_180018115
0x1800181f0  lea     rdi, [rbx+30h]
0x1800181f4  mov     [rsp+98h+arg_0], r13
0x1800181fc  test    esi, esi
0x1800181fe  jns     loc_1800182FC
0x180018204  mov     rax, [rdi]
0x180018207  movsx   edx, word ptr [rax+114h]
0x18001820e  mov     rcx, cs:qword_1800A41F0
0x180018215  lea     r8, [rsp+98h+arg_0]
0x18001821d  mov     rax, [rcx]
0x180018220  mov     rax, [rax+20h]
0x180018224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018229  test    eax, eax
0x18001822b  jns     short loc_180018297
0x18001822d  mov     [rsp+98h+arg_0], r12
0x180018235  test    dword ptr [r12], 120h
0x18001823d  jz      loc_18001819B
0x180018243  movups  xmm2, xmmword ptr [r12]
0x180018248  mov     [rsp+98h+var_70], r13d; unsigned int
0x18001824d  xor     r9d, r9d; struct IUndoBuilder *
0x180018250  movups  xmm0, xmmword ptr [r12+10h]
0x180018256  lea     rdx, [rsp+98h+var_68]; struct CCharFormat *
0x18001825b  xor     r8d, r8d; unsigned int
0x18001825e  movsd   xmm1, qword ptr [r12+20h]
0x180018265  mov     rcx, rbx; this
0x180018268  movd    eax, xmm2
0x18001826c  movups  [rsp+98h+var_68], xmm2
0x180018271  mov     [rsp+98h+var_78], 0FEFFFFFFh; unsigned int
0x180018279  and     eax, 0FFFFFEDFh
0x18001827e  movsd   [rsp+98h+var_48], xmm1
0x180018284  mov     dword ptr [rsp+98h+var_68], eax
0x180018288  movups  [rsp+98h+var_58], xmm0
0x18001828d  call    ?SetCharFormat@CTxtRange@@QEAAJPEBVCCharFormat@@KPEAVIUndoBuilder@@KK@Z; CTxtRange::SetCharFormat(CCharFormat const *,ulong,IUndoBuilder *,ulong,ulong)
0x180018292  jmp     loc_1800181A7
0x180018297  mov     r12, [rsp+98h+arg_0]
0x18001829f  jmp     short loc_180018235
0x1800182a1  mov     rdi, cs:qword_1800A41F0
0x1800182a8  mov     edx, esi
0x1800182aa  mov     rcx, rdi
0x1800182ad  mov     rax, [rdi]
0x1800182b0  mov     rax, [rax]
0x1800182b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182b8  mov     rax, [rdi]
0x1800182bb  mov     rcx, rdi
0x1800182be  movsx   edx, word ptr [rbx+60h]
0x1800182c2  mov     rax, [rax+8]
0x1800182c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182cb  mov     [rbx+60h], si
0x1800182cf  jmp     loc_1800181A7
0x1800182d4  test    dword ptr [rcx], 40000h
0x1800182da  jz      loc_18001816F
0x1800182e0  mov     esi, 0FFFFFFFFh
0x1800182e5  jmp     loc_180018184
0x1800182ea  lea     rdi, [rbx+30h]
0x1800182ee  jmp     loc_180018020
0x1800182f3  lea     rdi, [rbx+30h]
0x1800182f7  jmp     loc_180018124
0x1800182fc  mov     edx, esi
0x1800182fe  jmp     loc_18001820E
0x180018303  mov     r9, r13
0x180018306  jmp     loc_180017F9F
0x18001830b  mov     rax, r13
0x18001830e  jmp     loc_180017FF7
0x180018313  mov     rax, r13
0x180018316  jmp     loc_1800180FC
0x18001831b  mov     rax, r13
0x18001831e  jmp     loc_1800180B1
0x180018323  mov     esi, r15d
0x180018326  mov     rcx, r14
0x180018329  jmp     loc_180018154
0x18001832e  mov     [rsp+98h+arg_0], r13
0x180018336  mov     r15d, 0FFFFFFFFh
0x18001833c  jmp     loc_180018011
0x180018341  mov     esi, r15d
0x180018344  jmp     loc_180018184
0x180018349  test    byte ptr [rbx+62h], 40h
0x18001834d  jz      loc_180018184
0x180018353  movzx   eax, byte ptr [r14+4]
0x180018358  mov     edx, r13d
0x18001835b  sub     eax, 0B1h
0x180018360  cmp     eax, 1
0x180018363  movzx   eax, byte ptr [rcx+4]
0x180018367  mov     ecx, r13d
0x18001836a  setbe   dl
0x18001836d  sub     eax, 0B1h
0x180018372  cmp     eax, 1
0x180018375  setbe   cl
0x180018378  cmp     ecx, edx
0x18001837a  cmovnz  esi, r15d
0x18001837e  jmp     loc_180018184
```
