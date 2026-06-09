# BfpHandleNetworkQueryOpen

- ea: `0x1400150f0`
- end: `0x1400152e8`
- name: `BfpHandleNetworkQueryOpen`
- size: `504`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400157a0`

## callees

- `0x140004b90`
- `0x140004fc0`
- `0x1400150f0`

## import_xrefs

- `ntoskrnl!PsGetHostSilo` at `0x14001516c`
- `ntoskrnl!PsGetHostSilo` at `0x14001516c`
- `ntoskrnl!IoGetSilo` at `0x140015292`
- `ntoskrnl!IoGetSilo` at `0x140015292`
- `FLTMGR!FltQueryInformationByName` at `0x1400151d9`
- `FLTMGR!FltQueryInformationByName` at `0x1400151d9`

## pseudocode

```c
__int64 __fastcall BfpHandleNetworkQueryOpen(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5)
{
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 Silo; // rax
  int v12; // r8d
  __int64 v14; // rax
  char v15; // cl
  __int64 v16; // rax
  _BYTE v17[48]; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v18[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v19; // [rsp+90h] [rbp-70h]
  __int128 v20; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v21[5]; // [rsp+B0h] [rbp-50h] BYREF

  memset(v17, 0, 44);
  v20 = 0;
  memset(v21, 0, 0x48u);
  v19 = 1;
  memset(v18, 0, sizeof(v18));
  LOWORD(v18[0]) = 40;
  if ( a5 )
    Silo = IoGetSilo(a2);
  else
    Silo = PsGetHostSilo(v10, v9);
  v19 = Silo;
  *(_DWORD *)v17 = 48;
  *(_QWORD *)&v17[8] = 0;
  *(_DWORD *)&v17[24] = 512;
  *(_QWORD *)&v17[16] = a4;
  *(_OWORD *)&v17[32] = 0;
  v12 = FltQueryInformationByName(g_BindFltState, a3, v17, &v20, v21, 72, 68, v18);
  if ( v12 >= 0 )
  {
    v14 = *(_QWORD *)(a1 + 16);
    v15 = *(_BYTE *)(v14 + 4);
    if ( v15 == -14 )
    {
      *(_QWORD *)(*(_QWORD *)(v14 + 32) + 32LL) = *((_QWORD *)&v21[2] + 1);
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 32LL) + 24LL) = *(_QWORD *)&v21[2];
      **(_QWORD **)(*(_QWORD *)(a1 + 16) + 32LL) = *((_QWORD *)&v21[0] + 1);
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 32LL) + 40LL) = *(_QWORD *)&v21[3];
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 32LL) + 48LL) = DWORD2(v21[3]);
      *(_OWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 32LL) + 8LL) = v21[1];
    }
    else if ( v15 == -7 )
    {
      if ( *(_DWORD *)(v14 + 48) != 68 )
        return (unsigned int)-1073741637;
      v16 = *(_QWORD *)(v14 + 32);
      *(_OWORD *)v16 = v21[0];
      *(_OWORD *)(v16 + 16) = v21[1];
      *(_OWORD *)(v16 + 32) = v21[2];
      *(_OWORD *)(v16 + 48) = v21[3];
      *(_QWORD *)(v16 + 64) = *(_QWORD *)&v21[4];
    }
    *(_DWORD *)(a1 + 24) = 0;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400150f0  push    rbp
0x1400150f2  push    rbx
0x1400150f3  push    rsi
0x1400150f4  push    rdi
0x1400150f5  push    r14
0x1400150f7  lea     rbp, [rsp-10h]
0x1400150fc  sub     rsp, 110h
0x140015103  mov     rax, cs:__security_cookie
0x14001510a  xor     rax, rsp
0x14001510d  mov     [rbp+30h+var_30], rax
0x140015111  xorps   xmm0, xmm0
0x140015114  xor     eax, eax
0x140015116  mov     rsi, r8
0x140015119  mov     rdi, rdx
0x14001511c  mov     rbx, rcx
0x14001511f  xor     edx, edx; Val
0x140015121  movups  [rsp+130h+var_E0], xmm0
0x140015126  lea     r8d, [rax+48h]; Size
0x14001512a  mov     r14, r9
0x14001512d  lea     rcx, [rbp+30h+var_80]; void *
0x140015131  movups  [rsp+130h+var_F0], xmm0
0x140015136  movups  [rsp+130h+var_E0+0Ch], xmm0
0x14001513b  movups  [rbp+30h+var_98], xmm0
0x14001513f  call    memset
0x140015144  cmp     [rbp+30h+arg_20], 0
0x140015148  xorps   xmm0, xmm0
0x14001514b  mov     eax, 28h ; '('
0x140015150  mov     [rbp+30h+var_A0], 1
0x140015158  movups  [rsp+130h+var_C0], xmm0
0x14001515d  mov     word ptr [rsp+130h+var_C0], ax
0x140015162  movups  [rbp+30h+var_B0], xmm0
0x140015166  jnz     loc_14001528F
0x14001516c  call    cs:__imp_PsGetHostSilo
0x140015173  nop     dword ptr [rax+rax+00h]
0x140015178  mov     rcx, cs:g_BindFltState
0x14001517f  lea     r9, [rbp+30h+var_98]
0x140015183  mov     [rbp+30h+var_A0], rax
0x140015187  lea     r8, [rsp+130h+var_F0]
0x14001518c  lea     rax, [rsp+130h+var_C0]
0x140015191  mov     dword ptr [rsp+130h+var_F0], 30h ; '0'
0x140015199  mov     [rsp+130h+var_F8], rax
0x14001519e  xorps   xmm0, xmm0
0x1400151a1  mov     [rsp+130h+var_100], 44h ; 'D'
0x1400151a9  lea     rax, [rbp+30h+var_80]
0x1400151ad  mov     [rsp+130h+var_108], 48h ; 'H'
0x1400151b5  mov     rdx, rsi
0x1400151b8  mov     [rsp+130h+var_110], rax
0x1400151bd  mov     qword ptr [rsp+130h+var_F0+8], 0
0x1400151c6  mov     dword ptr [rsp+130h+var_E0+8], 200h
0x1400151ce  mov     qword ptr [rsp+130h+var_E0], r14
0x1400151d3  movdqu  [rsp+130h+var_D0], xmm0
0x1400151d9  call    cs:__imp_FltQueryInformationByName
0x1400151e0  nop     dword ptr [rax+rax+00h]
0x1400151e5  mov     r8d, eax
0x1400151e8  test    eax, eax
0x1400151ea  jns     short loc_14001520A
0x1400151ec  mov     eax, r8d
0x1400151ef  mov     rcx, [rbp+30h+var_30]
0x1400151f3  xor     rcx, rsp; StackCookie
0x1400151f6  call    __security_check_cookie
0x1400151fb  add     rsp, 110h
0x140015202  pop     r14
0x140015204  pop     rdi
0x140015205  pop     rsi
0x140015206  pop     rbx
0x140015207  pop     rbp
0x140015208  retn
0x14001520a  mov     rax, [rbx+10h]
0x14001520e  mov     cl, [rax+4]
0x140015211  cmp     cl, 0F2h
0x140015214  jnz     loc_1400152A3
0x14001521a  mov     rdx, [rax+20h]
0x14001521e  mov     rcx, qword ptr [rbp+30h+var_60+8]
0x140015222  mov     [rdx+20h], rcx
0x140015226  mov     rcx, [rbx+10h]
0x14001522a  mov     rax, qword ptr [rbp+30h+var_60]
0x14001522e  mov     rdx, [rcx+20h]
0x140015232  mov     [rdx+18h], rax
0x140015236  mov     rax, [rbx+10h]
0x14001523a  mov     rcx, [rax+20h]
0x14001523e  mov     rax, qword ptr [rbp+30h+var_80+8]
0x140015242  mov     [rcx], rax
0x140015245  mov     rax, [rbx+10h]
0x140015249  mov     rcx, [rax+20h]
0x14001524d  mov     rax, qword ptr [rbp+30h+var_50]
0x140015251  mov     [rcx+28h], rax
0x140015255  mov     rax, [rbx+10h]
0x140015259  mov     rcx, [rax+20h]
0x14001525d  mov     eax, dword ptr [rbp+30h+var_50+8]
0x140015260  mov     [rcx+30h], eax
0x140015263  mov     rax, [rbx+10h]
0x140015267  mov     rcx, [rax+20h]
0x14001526b  mov     rax, qword ptr [rbp+30h+var_70]
0x14001526f  mov     [rcx+8], rax
0x140015273  mov     rax, [rbx+10h]
0x140015277  mov     rcx, [rax+20h]
0x14001527b  mov     rax, qword ptr [rbp+30h+var_70+8]
0x14001527f  mov     [rcx+10h], rax
0x140015283  mov     dword ptr [rbx+18h], 0
0x14001528a  jmp     loc_1400151EC
0x14001528f  mov     rcx, rdi
0x140015292  call    cs:__imp_IoGetSilo
0x140015299  nop     dword ptr [rax+rax+00h]
0x14001529e  jmp     loc_140015178
0x1400152a3  cmp     cl, 0F9h
0x1400152a6  jnz     short loc_140015283
0x1400152a8  cmp     dword ptr [rax+30h], 44h ; 'D'
0x1400152ac  jnz     short loc_1400152DD
0x1400152ae  movaps  xmm0, [rbp+30h+var_80]
0x1400152b2  mov     rax, [rax+20h]
0x1400152b6  movups  xmmword ptr [rax], xmm0
0x1400152b9  movaps  xmm1, [rbp+30h+var_70]
0x1400152bd  movups  xmmword ptr [rax+10h], xmm1
0x1400152c1  movaps  xmm0, [rbp+30h+var_60]
0x1400152c5  movups  xmmword ptr [rax+20h], xmm0
0x1400152c9  movaps  xmm1, [rbp+30h+var_50]
0x1400152cd  movups  xmmword ptr [rax+30h], xmm1
0x1400152d1  movsd   xmm0, [rbp+30h+var_40]
0x1400152d6  movsd   qword ptr [rax+40h], xmm0
0x1400152db  jmp     short loc_140015283
0x1400152dd  mov     r8d, 0C00000BBh
0x1400152e3  jmp     loc_1400151EC
```
