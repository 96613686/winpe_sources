# CIISGenObject::IISCreateObject(void)

- ea: `0x180006660`
- end: `0x18000688e`
- name: `?IISCreateObject@CIISGenObject@@QEAAJXZ`
- size: `558`
- prototype: `__int64 __fastcall(CIISGenObject *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180007c50`

## callees

- `0x180006660`
- `0x180012ffc`
- `0x180013f94`
- `0x18001441c`
- `0x18001d6c0`
- `0x18001e010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000671e`
- `msvcrt!wcsrchr` at `0x18000671e`
- `msvcrt!wcscpy_s` at `0x1800066ff`
- `msvcrt!wcscpy_s` at `0x1800067e4`
- `msvcrt!wcscpy_s` at `0x1800066ff`
- `msvcrt!wcscpy_s` at `0x1800067e4`
- `ACTIVEDS!__imp_AllocADsMem` at `0x1800066ca`
- `ACTIVEDS!__imp_AllocADsMem` at `0x1800066ca`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180006863`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180006863`

## pseudocode

```c
__int64 __fastcall CIISGenObject::IISCreateObject(CIISGenObject *this)
{
  __int64 v1; // r12
  __int64 v3; // rax
  __int64 v4; // rcx
  unsigned int v5; // r14d
  unsigned int v6; // edi
  wchar_t *v7; // rax
  struct IMSAdminBaseW **v8; // rbx
  unsigned __int16 *v9; // rsi
  int v10; // edi
  const wchar_t *v11; // r8
  wchar_t *v12; // r13
  wchar_t *v13; // rax
  int v14; // eax
  wchar_t *v15; // r13
  const wchar_t *v16; // r8
  unsigned __int64 v17; // rax
  struct IMSAdminBaseW *v18; // rcx
  unsigned int v20; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *v21; // [rsp+38h] [rbp-C8h]
  __int128 v22; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v23; // [rsp+50h] [rbp-B0h]
  __int64 v24; // [rsp+60h] [rbp-A0h]
  wchar_t Destination[264]; // [rsp+70h] [rbp-90h] BYREF

  v24 = 0;
  v1 = -1;
  v20 = 0;
  v3 = -1;
  v4 = *((_QWORD *)this + 18);
  v5 = 0;
  v22 = 0;
  v23 = 0;
  do
    ++v3;
  while ( *(_WORD *)(v4 + 2 * v3) );
  v6 = v3 + 1;
  v7 = (wchar_t *)AllocADsMem(2 * ((int)v3 + 1));
  v8 = (struct IMSAdminBaseW **)((char *)this + 200);
  v9 = v7;
  if ( v7 )
  {
    v11 = (const wchar_t *)*((_QWORD *)this + 18);
    v12 = 0;
    v21 = 0;
    wcscpy_s(v7, v6, v11);
    while ( 1 )
    {
      v10 = MetaBaseDetectKey(*v8, v9);
      if ( v10 >= 0 )
        break;
      v13 = wcsrchr(v9, 0x2Fu);
      if ( !v13 )
        goto LABEL_23;
      if ( v12 )
        *v12 = 47;
      *v13 = 0;
      v21 = v13 + 1;
      v12 = v13;
    }
    v14 = OpenAdminBaseKey(
            (CIISGenObject *)((char *)this + 176),
            *((unsigned __int16 **)this + 17),
            v9,
            2u,
            (struct IMSAdminBaseW **)this + 25,
            &v20);
    v5 = v20;
    v10 = v14;
    if ( v14 >= 0 )
    {
      v15 = v21;
      if ( v21 )
        v10 = ((__int64 (__fastcall *)(struct IMSAdminBaseW *, _QWORD, wchar_t *))(*v8)->lpVtbl->AddKey)(*v8, v20, v21);
      if ( (_WORD)v10 == 183 || v10 >= 0 )
      {
        v16 = (const wchar_t *)*((_QWORD *)this + 5);
        v17 = -1;
        do
          ++v17;
        while ( v16[v17] );
        if ( v17 < 0x104 )
        {
          wcscpy_s(Destination, 0x104u, v16);
          *(_QWORD *)&v22 = 1002;
          *((_QWORD *)&v22 + 1) = 0x200000001LL;
          do
            ++v1;
          while ( Destination[v1] );
          v18 = *v8;
          LODWORD(v23) = 2 * v1 + 2;
          *((_QWORD *)&v23 + 1) = Destination;
          v10 = ((__int64 (__fastcall *)(struct IMSAdminBaseW *, _QWORD, wchar_t *, __int128 *))v18->lpVtbl->SetData)(
                  v18,
                  v5,
                  v15,
                  &v22);
        }
        else
        {
          v10 = -2147463160;
        }
      }
    }
  }
  else
  {
    v10 = -2147024882;
  }
LABEL_23:
  if ( *v8 && v5 )
    CloseAdminBaseKey(*v8, v5);
  if ( v9 )
    FreeADsMem(v9);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180006660  push    rbp
0x180006662  push    rbx
0x180006663  push    rsi
0x180006664  push    rdi
0x180006665  push    r12
0x180006667  push    r13
0x180006669  push    r14
0x18000666b  push    r15
0x18000666d  lea     rbp, [rsp-198h]
0x180006675  sub     rsp, 298h
0x18000667c  mov     rax, cs:__security_cookie
0x180006683  xor     rax, rsp
0x180006686  mov     [rbp+1D0h+var_50], rax
0x18000668d  xor     edx, edx
0x18000668f  xor     eax, eax
0x180006691  xorps   xmm0, xmm0
0x180006694  mov     [rsp+2D0h+var_270], rax
0x180006699  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000669d  mov     [rsp+2D0h+var_2A0], edx
0x1800066a1  mov     r15, rcx
0x1800066a4  mov     rax, r12
0x1800066a7  mov     rcx, [rcx+90h]
0x1800066ae  mov     r14d, edx
0x1800066b1  movups  [rsp+2D0h+var_290], xmm0
0x1800066b6  movups  [rsp+2D0h+var_280], xmm0
0x1800066bb  inc     rax
0x1800066be  cmp     [rcx+rax*2], dx
0x1800066c2  jnz     short loc_1800066BB
0x1800066c4  lea     edi, [rax+1]
0x1800066c7  lea     ecx, [rdi+rdi]; cb
0x1800066ca  call    cs:__imp_AllocADsMem
0x1800066d0  xor     edx, edx
0x1800066d2  lea     rbx, [r15+0C8h]
0x1800066d9  mov     rsi, rax
0x1800066dc  test    rax, rax
0x1800066df  jnz     short loc_1800066EB
0x1800066e1  mov     edi, 8007000Eh
0x1800066e6  jmp     loc_180006846
0x1800066eb  mov     r8, [r15+90h]; Source
0x1800066f2  mov     r13, rdx
0x1800066f5  mov     [rsp+2D0h+var_298], rdx
0x1800066fa  mov     rcx, rsi; Destination
0x1800066fd  mov     edx, edi; SizeInWords
0x1800066ff  call    cs:__imp_wcscpy_s
0x180006705  mov     rcx, [rbx]; struct IMSAdminBaseW *
0x180006708  mov     rdx, rsi; unsigned __int16 *
0x18000670b  call    ?MetaBaseDetectKey@@YAJPEAUIMSAdminBaseW@@PEBG@Z; MetaBaseDetectKey(IMSAdminBaseW *,ushort const *)
0x180006710  mov     edi, eax
0x180006712  test    eax, eax
0x180006714  jns     short loc_18000674C
0x180006716  mov     edx, 2Fh ; '/'; Ch
0x18000671b  mov     rcx, rsi; Str
0x18000671e  call    cs:__imp_wcsrchr
0x180006724  xor     edx, edx
0x180006726  test    rax, rax
0x180006729  jz      loc_180006846
0x18000672f  test    r13, r13
0x180006732  jz      short loc_18000673B
0x180006734  mov     word ptr [r13+0], 2Fh ; '/'
0x18000673b  lea     rcx, [rax+2]
0x18000673f  mov     [rax], dx
0x180006742  mov     [rsp+2D0h+var_298], rcx
0x180006747  mov     r13, rax
0x18000674a  jmp     short loc_180006705
0x18000674c  mov     rdx, [r15+88h]; unsigned __int16 *
0x180006753  lea     rax, [rsp+2D0h+var_2A0]
0x180006758  mov     [rsp+2D0h+var_2A8], rax; unsigned int *
0x18000675d  lea     rcx, [r15+0B0h]; this
0x180006764  mov     r9d, 2; unsigned int
0x18000676a  mov     [rsp+2D0h+var_2B0], rbx; struct IMSAdminBaseW **
0x18000676f  mov     r8, rsi; unsigned __int16 *
0x180006772  call    ?OpenAdminBaseKey@@YAJAEAVCCredentials@@PEAG1KPEAPEAUIMSAdminBaseW@@PEAK@Z; OpenAdminBaseKey(CCredentials &,ushort *,ushort *,ulong,IMSAdminBaseW * *,ulong *)
0x180006777  mov     r14d, [rsp+2D0h+var_2A0]
0x18000677c  xor     edx, edx
0x18000677e  mov     edi, eax
0x180006780  test    eax, eax
0x180006782  js      loc_180006846
0x180006788  mov     r13, [rsp+2D0h+var_298]
0x18000678d  test    r13, r13
0x180006790  jz      short loc_1800067AB
0x180006792  mov     rcx, [rbx]
0x180006795  mov     r8, r13
0x180006798  mov     edx, r14d
0x18000679b  mov     rax, [rcx]
0x18000679e  mov     rax, [rax+18h]
0x1800067a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067a7  mov     edi, eax
0x1800067a9  xor     edx, edx
0x1800067ab  cmp     di, 0B7h
0x1800067b0  jz      short loc_1800067BA
0x1800067b2  test    edi, edi
0x1800067b4  js      loc_180006846
0x1800067ba  mov     r8, [r15+28h]; Source
0x1800067be  mov     rax, r12
0x1800067c1  inc     rax
0x1800067c4  cmp     [r8+rax*2], dx
0x1800067c9  jnz     short loc_1800067C1
0x1800067cb  mov     ecx, 104h
0x1800067d0  cmp     rax, rcx
0x1800067d3  jb      short loc_1800067DC
0x1800067d5  mov     edi, 80005008h
0x1800067da  jmp     short loc_180006846
0x1800067dc  mov     rdx, rcx; SizeInWords
0x1800067df  lea     rcx, [rsp+2D0h+Destination]; Destination
0x1800067e4  call    cs:__imp_wcscpy_s
0x1800067ea  xor     edx, edx
0x1800067ec  mov     qword ptr [rsp+2D0h+var_290], 3EAh
0x1800067f5  lea     rax, [rsp+2D0h+Destination]
0x1800067fa  mov     dword ptr [rsp+2D0h+var_290+0Ch], 2
0x180006802  mov     dword ptr [rsp+2D0h+var_290+8], 1
0x18000680a  inc     r12
0x18000680d  cmp     [rax+r12*2], dx
0x180006812  jnz     short loc_18000680A
0x180006814  mov     rcx, [rbx]
0x180006817  lea     eax, ds:2[r12*2]
0x18000681f  mov     dword ptr [rsp+2D0h+var_280], eax
0x180006823  lea     r9, [rsp+2D0h+var_290]
0x180006828  lea     rax, [rsp+2D0h+Destination]
0x18000682d  mov     r8, r13
0x180006830  mov     qword ptr [rsp+2D0h+var_280+8], rax
0x180006835  mov     edx, r14d
0x180006838  mov     rax, [rcx]
0x18000683b  mov     rax, [rax+48h]
0x18000683f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006844  mov     edi, eax
0x180006846  mov     rcx, [rbx]; struct IMSAdminBaseW *
0x180006849  test    rcx, rcx
0x18000684c  jz      short loc_18000685B
0x18000684e  test    r14d, r14d
0x180006851  jz      short loc_18000685B
0x180006853  mov     edx, r14d; unsigned int
0x180006856  call    ?CloseAdminBaseKey@@YAXPEAUIMSAdminBaseW@@K@Z; CloseAdminBaseKey(IMSAdminBaseW *,ulong)
0x18000685b  test    rsi, rsi
0x18000685e  jz      short loc_180006869
0x180006860  mov     rcx, rsi; pMem
0x180006863  call    cs:__imp_FreeADsMem
0x180006869  mov     eax, edi
0x18000686b  mov     rcx, [rbp+1D0h+var_50]
0x180006872  xor     rcx, rsp; StackCookie
0x180006875  call    __security_check_cookie
0x18000687a  add     rsp, 298h
0x180006881  pop     r15
0x180006883  pop     r14
0x180006885  pop     r13
0x180006887  pop     r12
0x180006889  pop     rdi
0x18000688a  pop     rsi
0x18000688b  pop     rbx
0x18000688c  pop     rbp
0x18000688d  retn
```
