# SuGetSpaceTemplate(_SU_POOL_OBJECT *,_SC_SPACE_USAGE,_SP_RESILIENCY_TYPE,_SP_FD_IDS *,_SP_SPACE_INFO * *)

- ea: `0x140012fb0`
- end: `0x1400132aa`
- name: `?SuGetSpaceTemplate@@YAHPEAU_SU_POOL_OBJECT@@W4_SC_SPACE_USAGE@@W4_SP_RESILIENCY_TYPE@@PEAU_SP_FD_IDS@@PEAPEAU_SP_SPACE_INFO@@@Z`
- size: `762`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14000fb94`
- `0x140018a8c`

## callees

- `0x14000d29c`
- `0x14000e1c8`
- `0x140011f24`
- `0x140011f54`
- `0x140012fb0`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14001317f`
- `KERNEL32!LocalFree` at `0x14001317f`
- `KERNEL32!SetLastError` at `0x140013147`
- `KERNEL32!SetLastError` at `0x140013174`
- `KERNEL32!SetLastError` at `0x140013147`
- `KERNEL32!SetLastError` at `0x140013174`
- `KERNEL32!LocalAlloc` at `0x140013134`
- `KERNEL32!LocalAlloc` at `0x140013134`
- `RPCRT4!UuidCreate` at `0x140013168`
- `RPCRT4!UuidCreate` at `0x140013168`

## pseudocode

```c
__int64 __fastcall SuGetSpaceTemplate(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, _QWORD *a5)
{
  char v7; // r8
  char v8; // dl
  __int16 v9; // si
  __int16 v10; // di
  char v11; // bl
  char v12; // r11
  char v13; // r10
  char v14; // r9
  int v15; // r14d
  char v16; // cl
  char v17; // al
  unsigned int Drives; // edi
  __int64 v19; // r9
  struct _LIST_ENTRY *Flink; // rax
  int i; // edi
  char *v22; // rax
  char *v23; // rbx
  RPC_STATUS v24; // eax
  struct _LIST_ENTRY *v25; // rcx
  struct _LIST_ENTRY *v26; // rax
  unsigned int v27; // eax
  char *v28; // rcx
  struct _LIST_ENTRY *j; // rax
  __int64 v30; // rdx
  __int64 v31; // rcx
  struct _LIST_ENTRY v33; // [rsp+30h] [rbp-91h] BYREF
  __int128 v34; // [rsp+40h] [rbp-81h] BYREF
  int v35; // [rsp+50h] [rbp-71h]
  _DWORD v36[2]; // [rsp+58h] [rbp-69h] BYREF
  __int16 v37; // [rsp+60h] [rbp-61h]
  __int16 v38; // [rsp+62h] [rbp-5Fh]
  char v39; // [rsp+64h] [rbp-5Dh]
  char v40; // [rsp+65h] [rbp-5Ch]
  char v41; // [rsp+66h] [rbp-5Bh]
  char v42; // [rsp+67h] [rbp-5Ah]
  char v43; // [rsp+68h] [rbp-59h]
  char v44; // [rsp+69h] [rbp-58h]
  char v45; // [rsp+6Ah] [rbp-57h]
  char v46; // [rsp+6Bh] [rbp-56h]
  __int64 v47; // [rsp+6Ch] [rbp-55h]
  __int64 v48; // [rsp+74h] [rbp-4Dh]
  __int16 v49; // [rsp+7Ch] [rbp-45h]
  char v50; // [rsp+7Eh] [rbp-43h]
  _DWORD v51[2]; // [rsp+80h] [rbp-41h] BYREF
  __int16 v52; // [rsp+88h] [rbp-39h]
  __int16 v53; // [rsp+8Ah] [rbp-37h]
  char v54; // [rsp+8Ch] [rbp-35h]
  char v55; // [rsp+8Dh] [rbp-34h]
  char v56; // [rsp+8Eh] [rbp-33h]
  char v57; // [rsp+8Fh] [rbp-32h]
  char v58; // [rsp+90h] [rbp-31h]
  char v59; // [rsp+91h] [rbp-30h]
  char v60; // [rsp+92h] [rbp-2Fh]
  char v61; // [rsp+93h] [rbp-2Eh]
  __int16 v62; // [rsp+94h] [rbp-2Dh]
  char v63; // [rsp+96h] [rbp-2Bh]
  char v64; // [rsp+98h] [rbp-29h]
  char v65; // [rsp+A0h] [rbp-21h]
  char v66; // [rsp+A8h] [rbp-19h]

  v49 = 256;
  v64 = 0;
  v35 = 0;
  *a5 = 0;
  v7 = *(_BYTE *)(a1 + 52);
  v8 = *(_BYTE *)(a1 + 53);
  v9 = *(_WORD *)(a1 + 44);
  v10 = *(_WORD *)(a1 + 46);
  v11 = *(_BYTE *)(a1 + 48);
  v12 = *(_BYTE *)(a1 + 49);
  v13 = *(_BYTE *)(a1 + 50);
  v14 = *(_BYTE *)(a1 + 51);
  v15 = *(_DWORD *)(a1 + 40);
  v33.Blink = &v33;
  v65 = 0;
  v66 = 0;
  v47 = 0;
  v48 = 0;
  v50 = 0;
  v16 = *(_BYTE *)(a1 + 54);
  v33.Flink = &v33;
  v17 = *(_BYTE *)(a1 + 55);
  v58 = v7;
  v59 = v8;
  v60 = v16;
  v43 = v7;
  v44 = v8;
  v45 = v16;
  v61 = v17;
  v46 = v17;
  v34 = 0;
  v51[0] = 64;
  v51[1] = v15;
  v52 = v9;
  v53 = v10;
  v54 = v11;
  v55 = v12;
  v56 = v13;
  v57 = v14;
  v62 = 257;
  v63 = 1;
  v36[0] = 40;
  v36[1] = v15;
  v37 = v9;
  v38 = v10;
  v39 = v11;
  v40 = v12;
  v41 = v13;
  v42 = v14;
  Drives = SuGetDrives((struct SP_DRIVE_ENUM_FILTER *)v51, (struct SP_DRIVE_PROP_FILTER *)v36, &v33);
  if ( Drives )
  {
    Drives = SiSelectMetadataDrives(*(_DWORD *)(a1 + 2644), (__int64)&v34, 0, v19, (__int64 *)&v33);
    if ( Drives )
    {
      Flink = v33.Flink;
      for ( i = 0; Flink != &v33; Flink = Flink->Flink )
      {
        if ( (BYTE4(Flink[1].Flink) & 4) != 0 )
          ++i;
      }
      v22 = (char *)LocalAlloc(0x40u, (unsigned int)(16 * i + 3032));
      v23 = v22;
      if ( !v22 )
      {
        SetLastError(0x5AAu);
        Drives = 0;
        goto LABEL_13;
      }
      *(_DWORD *)v22 = 3032;
      *((_DWORD *)v22 + 1) = 16 * i + 3032;
      *(_OWORD *)(v22 + 8) = *(_OWORD *)(a1 + 40);
      v24 = UuidCreate((UUID *)(v22 + 24));
      if ( v24 )
      {
        SetLastError(v24);
        Drives = 0;
LABEL_11:
        v25 = (struct _LIST_ENTRY *)v23;
        goto LABEL_12;
      }
      v27 = 16 * *((_DWORD *)v23 + 683) + 3032;
      v23[2600] = 2;
      *((_DWORD *)v23 + 685) = i;
      v28 = &v23[v27];
      *((_DWORD *)v23 + 686) = v27;
      for ( j = v33.Flink; j != &v33; j = j->Flink )
      {
        if ( (BYTE4(j[1].Flink) & 4) != 0 )
        {
          *(struct _LIST_ENTRY *)v28 = *(struct _LIST_ENTRY *)((char *)j + 56);
          v28 += 16;
        }
      }
      if ( !a3 )
        a3 = *(_DWORD *)(a1 + 2776);
      Drives = SiInitializeProvisioning(a1, a3, v23 + 2696);
      if ( !Drives )
        goto LABEL_11;
      Drives = SiInitializeResiliency(v31, v30, v23 + 2748);
      if ( !Drives )
        goto LABEL_11;
      *(_OWORD *)(v23 + 2776) = *(_OWORD *)(a1 + 2856);
      *((_QWORD *)v23 + 349) = *(_QWORD *)(a1 + 2872);
      *((_DWORD *)v23 + 700) = 1;
      *a5 = v23;
    }
  }
LABEL_13:
  while ( 1 )
  {
    v25 = v33.Flink;
    if ( v33.Flink == &v33 )
      break;
    if ( v33.Flink->Blink != &v33 || (v26 = v33.Flink->Flink, v33.Flink->Flink->Blink != v33.Flink) )
      __fastfail(3u);
    v33.Flink = v33.Flink->Flink;
    v26->Blink = &v33;
LABEL_12:
    LocalFree(v25);
  }
  return Drives;
}

```

## disassembly

```asm
0x140012fb0  push    rbp
0x140012fb2  push    rbx
0x140012fb3  push    rsi
0x140012fb4  push    rdi
0x140012fb5  push    r12
0x140012fb7  push    r13
0x140012fb9  push    r14
0x140012fbb  push    r15
0x140012fbd  lea     rbp, [rsp-17h]
0x140012fc2  sub     rsp, 0D8h
0x140012fc9  mov     rax, cs:__security_cookie
0x140012fd0  xor     rax, rsp
0x140012fd3  mov     [rbp+4Fh+var_50], rax
0x140012fd7  mov     r13, [rbp+4Fh+arg_20]
0x140012fdb  mov     r15, rcx
0x140012fde  xor     ecx, ecx
0x140012fe0  mov     [rbp+4Fh+var_94], 100h
0x140012fe6  xor     eax, eax
0x140012fe8  mov     [rbp+4Fh+var_78], cl
0x140012feb  mov     [rbp+4Fh+var_C0], eax
0x140012fee  mov     r12d, r8d
0x140012ff1  mov     [r13+0], rcx
0x140012ff5  lea     rax, [rsp+110h+var_E0]
0x140012ffa  mov     r8b, [r15+34h]
0x140012ffe  xorps   xmm0, xmm0
0x140013001  mov     dl, [r15+35h]
0x140013005  movzx   esi, word ptr [r15+2Ch]
0x14001300a  movzx   edi, word ptr [r15+2Eh]
0x14001300f  mov     bl, [r15+30h]
0x140013013  mov     r11b, [r15+31h]
0x140013017  mov     r10b, [r15+32h]
0x14001301b  mov     r9b, [r15+33h]
0x14001301f  mov     r14d, [r15+28h]
0x140013023  mov     [rsp+110h+var_E0.Blink], rax
0x140013028  lea     rax, [rsp+110h+var_E0]
0x14001302d  mov     [rbp+4Fh+var_70], cl
0x140013030  mov     [rbp+4Fh+var_68], cl
0x140013033  mov     [rbp+4Fh+var_A4], rcx
0x140013037  mov     [rbp+4Fh+var_9C], rcx
0x14001303b  mov     [rbp+4Fh+var_92], cl
0x14001303e  mov     cl, [r15+36h]
0x140013042  mov     [rsp+110h+var_E0.Flink], rax
0x140013047  mov     al, [r15+37h]
0x14001304b  mov     [rbp+4Fh+var_80], r8b
0x14001304f  mov     [rbp+4Fh+var_7F], dl
0x140013052  mov     [rbp+4Fh+var_7E], cl
0x140013055  mov     [rbp+4Fh+var_A8], r8b
0x140013059  lea     r8, [rsp+110h+var_E0]; struct _LIST_ENTRY *
0x14001305e  mov     [rbp+4Fh+var_A7], dl
0x140013061  lea     rdx, [rbp+4Fh+var_B8]; struct SP_DRIVE_PROP_FILTER *
0x140013065  mov     [rbp+4Fh+var_A6], cl
0x140013068  lea     rcx, [rbp+4Fh+var_90]; struct SP_DRIVE_ENUM_FILTER *
0x14001306c  mov     [rbp+4Fh+var_7D], al
0x14001306f  mov     [rbp+4Fh+var_A5], al
0x140013072  movups  [rsp+110h+var_D0], xmm0
0x140013077  mov     [rbp+4Fh+var_90], 40h ; '@'
0x14001307e  mov     [rbp+4Fh+var_8C], r14d
0x140013082  mov     [rbp+4Fh+var_88], si
0x140013086  mov     [rbp+4Fh+var_86], di
0x14001308a  mov     [rbp+4Fh+var_84], bl
0x14001308d  mov     [rbp+4Fh+var_83], r11b
0x140013091  mov     [rbp+4Fh+var_82], r10b
0x140013095  mov     [rbp+4Fh+var_81], r9b
0x140013099  mov     [rbp+4Fh+var_7C], 101h
0x14001309f  mov     [rbp+4Fh+var_7A], 1
0x1400130a3  mov     [rbp+4Fh+var_B8], 28h ; '('
0x1400130aa  mov     [rbp+4Fh+var_B4], r14d
0x1400130ae  mov     [rbp+4Fh+var_B0], si
0x1400130b2  mov     [rbp+4Fh+var_AE], di
0x1400130b6  mov     [rbp+4Fh+var_AC], bl
0x1400130b9  mov     [rbp+4Fh+var_AB], r11b
0x1400130bd  mov     [rbp+4Fh+var_AA], r10b
0x1400130c1  mov     [rbp+4Fh+var_A9], r9b
0x1400130c5  call    ?SuGetDrives@@YAHPEAVSP_DRIVE_ENUM_FILTER@@PEAVSP_DRIVE_PROP_FILTER@@PEAU_LIST_ENTRY@@@Z; SuGetDrives(SP_DRIVE_ENUM_FILTER *,SP_DRIVE_PROP_FILTER *,_LIST_ENTRY *)
0x1400130ca  mov     edi, eax
0x1400130cc  test    eax, eax
0x1400130ce  jz      loc_140013185
0x1400130d4  mov     ecx, [r15+0A54h]
0x1400130db  lea     rax, [rsp+110h+var_E0]
0x1400130e0  xor     r8d, r8d
0x1400130e3  mov     [rsp+110h+var_F0], rax
0x1400130e8  lea     rdx, [rsp+110h+var_D0]
0x1400130ed  call    ?SiSelectMetadataDrives@@YAHW4_SC_VERSION@@PEAU_SP_IDS@@PEAU_SP_FD_IDS@@1PEAU_LIST_ENTRY@@@Z; SiSelectMetadataDrives(_SC_VERSION,_SP_IDS *,_SP_FD_IDS *,_SP_IDS *,_LIST_ENTRY *)
0x1400130f2  mov     edi, eax
0x1400130f4  test    eax, eax
0x1400130f6  jz      loc_140013185
0x1400130fc  mov     rax, [rsp+110h+var_E0.Flink]
0x140013101  lea     rcx, [rsp+110h+var_E0]
0x140013106  xor     edi, edi
0x140013108  cmp     rax, rcx
0x14001310b  jz      short loc_140013122
0x14001310d  test    byte ptr [rax+14h], 4
0x140013111  jz      short loc_140013115
0x140013113  inc     edi
0x140013115  mov     rax, [rax]
0x140013118  lea     rdx, [rsp+110h+var_E0]
0x14001311d  cmp     rax, rdx
0x140013120  jnz     short loc_14001310D
0x140013122  mov     esi, edi
0x140013124  mov     ecx, 40h ; '@'; uFlags
0x140013129  shl     esi, 4
0x14001312c  add     esi, 0BD8h
0x140013132  mov     edx, esi; uBytes
0x140013134  call    cs:__imp_LocalAlloc
0x14001313a  mov     rbx, rax
0x14001313d  test    rax, rax
0x140013140  jnz     short loc_140013151
0x140013142  mov     ecx, 5AAh; dwErrCode
0x140013147  call    cs:__imp_SetLastError
0x14001314d  xor     edi, edi
0x14001314f  jmp     short loc_140013185
0x140013151  mov     dword ptr [rax], 0BD8h
0x140013157  lea     rcx, [rax+18h]; Uuid
0x14001315b  mov     [rax+4], esi
0x14001315e  movups  xmm0, xmmword ptr [r15+28h]
0x140013163  movdqu  xmmword ptr [rax+8], xmm0
0x140013168  call    cs:__imp_UuidCreate
0x14001316e  test    eax, eax
0x140013170  jz      short loc_1400131C4
0x140013172  mov     ecx, eax; dwErrCode
0x140013174  call    cs:__imp_SetLastError
0x14001317a  xor     edi, edi
0x14001317c  mov     rcx, rbx; hMem
0x14001317f  call    cs:__imp_LocalFree
0x140013185  mov     rcx, [rsp+110h+var_E0.Flink]
0x14001318a  lea     rax, [rsp+110h+var_E0]
0x14001318f  cmp     rcx, rax
0x140013192  jz      loc_140013288
0x140013198  lea     rax, [rsp+110h+var_E0]
0x14001319d  cmp     [rcx+8], rax
0x1400131a1  jnz     loc_140013281
0x1400131a7  mov     rax, [rcx]
0x1400131aa  cmp     [rax+8], rcx
0x1400131ae  jnz     loc_140013281
0x1400131b4  lea     rdx, [rsp+110h+var_E0]
0x1400131b9  mov     [rsp+110h+var_E0.Flink], rax
0x1400131be  mov     [rax+8], rdx
0x1400131c2  jmp     short loc_14001317F
0x1400131c4  mov     eax, [rbx+0AACh]
0x1400131ca  shl     eax, 4
0x1400131cd  add     eax, 0BD8h
0x1400131d2  mov     byte ptr [rbx+0A28h], 2
0x1400131d9  mov     ecx, eax
0x1400131db  mov     [rbx+0AB4h], edi
0x1400131e1  add     rcx, rbx
0x1400131e4  mov     [rbx+0AB8h], eax
0x1400131ea  mov     rax, [rsp+110h+var_E0.Flink]
0x1400131ef  jmp     short loc_140013206
0x1400131f1  test    byte ptr [rax+14h], 4
0x1400131f5  jz      short loc_140013203
0x1400131f7  movups  xmm0, xmmword ptr [rax+38h]
0x1400131fb  movdqu  xmmword ptr [rcx], xmm0
0x1400131ff  add     rcx, 10h
0x140013203  mov     rax, [rax]
0x140013206  lea     rdx, [rsp+110h+var_E0]
0x14001320b  cmp     rax, rdx
0x14001320e  jnz     short loc_1400131F1
0x140013210  test    r12d, r12d
0x140013213  jnz     short loc_14001321C
0x140013215  mov     r12d, [r15+0AD8h]
0x14001321c  lea     r8, [rbx+0A88h]
0x140013223  mov     edx, r12d
0x140013226  mov     rcx, r15
0x140013229  call    ?SiInitializeProvisioning@@YAHPEAU_SU_POOL_OBJECT@@W4_SP_RESILIENCY_TYPE@@PEAU_SP_PROVISIONING_INFO@@@Z; SiInitializeProvisioning(_SU_POOL_OBJECT *,_SP_RESILIENCY_TYPE,_SP_PROVISIONING_INFO *)
0x14001322e  mov     edi, eax
0x140013230  test    eax, eax
0x140013232  jz      loc_14001317C
0x140013238  lea     r8, [rbx+0ABCh]
0x14001323f  call    ?SiInitializeResiliency@@YAHPEAU_SU_POOL_OBJECT@@W4_SP_RESILIENCY_TYPE@@PEAVSP_RESILIENCY_INFO@@@Z; SiInitializeResiliency(_SU_POOL_OBJECT *,_SP_RESILIENCY_TYPE,SP_RESILIENCY_INFO *)
0x140013244  mov     edi, eax
0x140013246  test    eax, eax
0x140013248  jz      loc_14001317C
0x14001324e  movups  xmm0, xmmword ptr [r15+0B28h]
0x140013256  movups  xmmword ptr [rbx+0AD8h], xmm0
0x14001325d  movsd   xmm1, qword ptr [r15+0B38h]
0x140013266  movsd   qword ptr [rbx+0AE8h], xmm1
0x14001326e  mov     dword ptr [rbx+0AF0h], 1
0x140013278  mov     [r13+0], rbx
0x14001327c  jmp     loc_140013185
0x140013281  mov     ecx, 3
0x140013286  int     29h; Win8: RtlFailFast(ecx)
0x140013288  mov     eax, edi
0x14001328a  mov     rcx, [rbp+4Fh+var_50]
0x14001328e  xor     rcx, rsp; StackCookie
0x140013291  call    __security_check_cookie
0x140013296  add     rsp, 0D8h
0x14001329d  pop     r15
0x14001329f  pop     r14
0x1400132a1  pop     r13
0x1400132a3  pop     r12
0x1400132a5  pop     rdi
0x1400132a6  pop     rsi
0x1400132a7  pop     rbx
0x1400132a8  pop     rbp
0x1400132a9  retn
```
