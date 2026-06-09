# SITE_OBJECT::CheckFriendlySiteIdMatch(ushort const *,int *)

- ea: `0x18001042c`
- end: `0x180010848`
- name: `?CheckFriendlySiteIdMatch@SITE_OBJECT@@AEAAJPEBGPEAH@Z`
- size: `1052`
- prototype: `int(SITE_OBJECT *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180011fe0`

## callees

- `0x180001fb0`
- `0x180002e90`
- `0x180002ed0`
- `0x180010200`
- `0x18001042c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180010541`
- `msvcrt!wcsstr` at `0x180010541`
- `msvcrt!wcschr` at `0x1800106ab`
- `msvcrt!wcschr` at `0x1800106ab`
- `msvcrt!_wcsicmp` at `0x180010649`
- `msvcrt!_wcsicmp` at `0x1800106fb`
- `msvcrt!_wcsicmp` at `0x180010718`
- `msvcrt!_wcsicmp` at `0x180010649`
- `msvcrt!_wcsicmp` at `0x1800106fb`
- `msvcrt!_wcsicmp` at `0x180010718`

## string_xrefs

- `0x180010624`: `protocol`

## pseudocode

```c
__int64 __fastcall SITE_OBJECT::CheckFriendlySiteIdMatch(SITE_OBJECT *this, const unsigned __int16 *a2, int *a3)
{
  __int64 v6; // rsi
  __int64 v7; // rdi
  unsigned __int16 *v8; // r13
  wchar_t *v9; // rsi
  int v10; // ebx
  unsigned int v11; // r14d
  wchar_t *v12; // r15
  const wchar_t *v13; // rsi
  wchar_t v14; // ax
  const unsigned __int16 *v15; // rbx
  wchar_t *v16; // rax
  wchar_t *v17; // rdi
  const unsigned __int16 *v18; // rdx
  SITE_OBJECT *v19; // rcx
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v23; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *String1; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v27; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v28[32]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v29; // [rsp+80h] [rbp-80h]
  int v30; // [rsp+88h] [rbp-78h]
  __int16 v31; // [rsp+8Ch] [rbp-74h]
  int v32; // [rsp+90h] [rbp-70h]
  _BYTE v33[32]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v34; // [rsp+B8h] [rbp-48h]
  int v35; // [rsp+C0h] [rbp-40h]
  __int16 v36; // [rsp+C4h] [rbp-3Ch]
  int v37; // [rsp+C8h] [rbp-38h]
  _BYTE v38[32]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t *String2; // [rsp+F0h] [rbp-10h]
  int v40; // [rsp+F8h] [rbp-8h]
  __int16 v41; // [rsp+FCh] [rbp-4h]
  int v42; // [rsp+100h] [rbp+0h]
  __int16 v43; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v44[126]; // [rsp+112h] [rbp+12h] BYREF
  unsigned __int16 v45; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v46[126]; // [rsp+192h] [rbp+92h] BYREF
  __int16 v47; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v48[126]; // [rsp+212h] [rbp+112h] BYREF

  v25 = 0;
  v22 = 0;
  v21 = 0;
  v23 = 0;
  String1 = 0;
  v27 = 0;
  v6 = 0;
  v7 = 0;
  memset_0(v44, 0, sizeof(v44));
  v36 = 256;
  v34 = (unsigned __int16 *)&v43;
  v35 = 128;
  v37 = 0;
  v43 = 0;
  memset_0(v46, 0, sizeof(v46));
  v30 = 128;
  v8 = &v45;
  v32 = 0;
  v45 = 0;
  v29 = &v45;
  v31 = 256;
  memset_0(v48, 0, sizeof(v48));
  v40 = 128;
  String2 = (wchar_t *)&v47;
  v41 = 256;
  v42 = 0;
  v47 = 0;
  if ( a2 && a3 )
  {
    *a3 = 0;
    v9 = wcsstr(a2, L"://");
    v10 = STRU::Copy((STRU *)v38, a2, v9 - a2);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64 *))(**((_QWORD **)this + 23) + 32LL))(
              *((_QWORD *)this + 23),
              L"bindings",
              &v25);
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 40LL))(v25, &v22);
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v22 + 24LL))(v22, &v23);
          if ( v10 >= 0 )
          {
            v7 = v21;
            v11 = 0;
            v12 = String2;
            v13 = v9 + 3;
            while ( 1 )
            {
              if ( v11 >= v23 )
              {
LABEL_29:
                v6 = v22;
                v10 = 0;
                goto LABEL_32;
              }
              v7 = 0;
              v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v22 + 32LL))(v22, v11, &v21);
              if ( v10 < 0 )
                goto LABEL_30;
              v10 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v21 + 64LL))(
                      v21,
                      L"protocol",
                      &String1,
                      0,
                      0);
              if ( v10 < 0 )
                goto LABEL_30;
              if ( !_wcsicmp(String1, v12) )
                break;
LABEL_27:
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
              ++v11;
              v21 = 0;
            }
            v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v21 + 64LL))(
                    v21,
                    L"bindingInformation",
                    &v27,
                    0,
                    0);
            if ( v10 < 0 )
              goto LABEL_30;
            v14 = 91;
            v15 = v13;
            if ( *v13 == 91 )
            {
              do
              {
                if ( !v14 )
                  break;
                v14 = *++v13;
              }
              while ( *v13 != 93 );
            }
            v16 = wcschr(v13, 0x3Au);
            v17 = v16;
            if ( v16 )
            {
              v10 = STRU::Copy((STRU *)v33, v15, v16 - v15);
              if ( v10 < 0 )
                goto LABEL_30;
              v18 = v17 + 1;
              v7 = 0;
            }
            else
            {
              v7 = 0;
              v10 = STRU::Copy((STRU *)v33, v15);
              if ( v10 < 0 )
                goto LABEL_30;
              if ( _wcsicmp(v12, L"http") )
              {
                if ( _wcsicmp(v12, L"https") )
                  goto LABEL_26;
                v18 = L"443";
              }
              else
              {
                v18 = L"80";
              }
            }
            v10 = STRU::Copy((STRU *)v28, v18);
            if ( v10 < 0 )
              goto LABEL_30;
            v8 = v29;
LABEL_26:
            v24 = 0;
            SITE_OBJECT::BindingInformationMatch(v19, v27, v34, v8, &v24);
            if ( v24 )
            {
              v7 = v21;
              *a3 = 1;
              goto LABEL_29;
            }
            goto LABEL_27;
          }
        }
      }
    }
LABEL_30:
    v6 = v22;
    v7 = v21;
  }
  else
  {
    v10 = -2147024809;
  }
LABEL_32:
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v6 = v22;
    v21 = 0;
  }
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    v22 = 0;
  }
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v38);
  BUFFER::~BUFFER((BUFFER *)v28);
  BUFFER::~BUFFER((BUFFER *)v33);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001042c  mov     [rsp-8+arg_18], rbx
0x180010431  push    rbp
0x180010432  push    rsi
0x180010433  push    rdi
0x180010434  push    r12
0x180010436  push    r13
0x180010438  push    r14
0x18001043a  push    r15
0x18001043c  lea     rbp, [rsp-1A0h]
0x180010444  sub     rsp, 2A0h
0x18001044b  mov     rax, cs:__security_cookie
0x180010452  xor     rax, rsp
0x180010455  mov     [rbp+1D0h+var_40], rax
0x18001045c  xor     eax, eax
0x18001045e  mov     r12, r8
0x180010461  mov     rbx, rdx
0x180010464  mov     [rsp+2D0h+var_288], rax
0x180010469  mov     r14, rcx
0x18001046c  mov     [rsp+2D0h+var_298], rax
0x180010471  xor     edx, edx; Val
0x180010473  mov     [rsp+2D0h+var_2A0], rax
0x180010478  lea     r13d, [rax+7Eh]
0x18001047c  mov     [rsp+2D0h+var_290], eax
0x180010480  mov     r8d, r13d; Size
0x180010483  mov     [rsp+2D0h+String1], rax
0x180010488  lea     rcx, [rbp+1D0h+var_1BE]; void *
0x18001048c  mov     [rsp+2D0h+var_278], rax
0x180010491  mov     esi, eax
0x180010493  mov     edi, eax
0x180010495  call    memset_0
0x18001049a  lea     rax, [rbp+1D0h+var_1C0]
0x18001049e  mov     [rbp+1D0h+var_20C], 100h
0x1800104a4  mov     [rbp+1D0h+var_218], rax
0x1800104a8  lea     r15d, [r13+2]
0x1800104ac  xor     eax, eax
0x1800104ae  mov     [rbp+1D0h+var_210], r15d
0x1800104b2  mov     r8d, r13d; Size
0x1800104b5  mov     [rbp+1D0h+var_208], eax
0x1800104b8  xor     edx, edx; Val
0x1800104ba  mov     [rbp+1D0h+var_1C0], ax
0x1800104be  lea     rcx, [rbp+1D0h+var_13E]; void *
0x1800104c5  call    memset_0
0x1800104ca  xor     eax, eax
0x1800104cc  mov     [rbp+1D0h+var_248], r15d
0x1800104d0  lea     r13, [rbp+1D0h+var_140]
0x1800104d7  mov     [rbp+1D0h+var_240], eax
0x1800104da  xor     edx, edx; Val
0x1800104dc  mov     [rbp+1D0h+var_140], ax
0x1800104e3  lea     r8d, [rdi+7Eh]; Size
0x1800104e7  mov     [rbp+1D0h+var_250], r13
0x1800104eb  lea     rcx, [rbp+1D0h+var_BE]; void *
0x1800104f2  mov     [rbp+1D0h+var_244], 100h
0x1800104f8  call    memset_0
0x1800104fd  mov     [rbp+1D0h+var_1D8], r15d
0x180010501  lea     rax, [rbp+1D0h+var_C0]
0x180010508  xor     r15d, r15d
0x18001050b  mov     [rbp+1D0h+String2], rax
0x18001050f  mov     [rbp+1D0h+var_1D4], 100h
0x180010515  mov     [rbp+1D0h+var_1D0], r15d
0x180010519  mov     [rbp+1D0h+var_C0], r15w
0x180010521  test    rbx, rbx
0x180010524  jz      loc_1800107A9
0x18001052a  test    r12, r12
0x18001052d  jz      loc_1800107A9
0x180010533  lea     rdx, asc_18003A618; "://"
0x18001053a  mov     [r12], r15d
0x18001053e  mov     rcx, rbx; Str
0x180010541  call    cs:__imp_wcsstr
0x180010547  mov     rdx, rbx; unsigned __int16 *
0x18001054a  lea     rcx, [rbp+1D0h+var_200]; this
0x18001054e  mov     r8, rax
0x180010551  mov     rsi, rax
0x180010554  sub     r8, rbx
0x180010557  sar     r8, 1; unsigned int
0x18001055a  call    ?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18001055f  mov     ebx, eax
0x180010561  test    eax, eax
0x180010563  js      loc_18001079D
0x180010569  mov     rcx, [r14+0B8h]
0x180010570  lea     r8, [rsp+2D0h+var_288]
0x180010575  mov     rdx, [rcx]
0x180010578  mov     rax, [rdx+20h]
0x18001057c  lea     rdx, aBindings_0; "bindings"
0x180010583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010588  mov     ebx, eax
0x18001058a  test    eax, eax
0x18001058c  js      loc_18001079D
0x180010592  mov     rcx, [rsp+2D0h+var_288]
0x180010597  lea     rdx, [rsp+2D0h+var_298]
0x18001059c  mov     rax, [rcx]
0x18001059f  mov     rax, [rax+28h]
0x1800105a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105a8  mov     ebx, eax
0x1800105aa  test    eax, eax
0x1800105ac  js      loc_18001079D
0x1800105b2  mov     rcx, [rsp+2D0h+var_298]
0x1800105b7  lea     rdx, [rsp+2D0h+var_290]
0x1800105bc  mov     rax, [rcx]
0x1800105bf  mov     rax, [rax+18h]
0x1800105c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105c8  mov     ebx, eax
0x1800105ca  test    eax, eax
0x1800105cc  js      loc_18001079D
0x1800105d2  mov     rdi, [rsp+2D0h+var_2A0]
0x1800105d7  mov     r14d, r15d
0x1800105da  mov     r15, [rbp+1D0h+String2]
0x1800105de  add     rsi, 6
0x1800105e2  cmp     r14d, [rsp+2D0h+var_290]
0x1800105e7  jnb     loc_18001078D
0x1800105ed  mov     rcx, [rsp+2D0h+var_298]
0x1800105f2  lea     r8, [rsp+2D0h+var_2A0]
0x1800105f7  mov     edx, r14d
0x1800105fa  mov     rax, [rcx]
0x1800105fd  mov     rax, [rax+20h]
0x180010601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010606  xor     edi, edi
0x180010608  mov     ebx, eax
0x18001060a  test    eax, eax
0x18001060c  js      loc_18001079A
0x180010612  mov     rcx, [rsp+2D0h+var_2A0]
0x180010617  lea     r8, [rsp+2D0h+String1]
0x18001061c  xor     r9d, r9d
0x18001061f  mov     [rsp+2D0h+var_2B0], rdi
0x180010624  lea     rdx, aProtocol; "protocol"
0x18001062b  mov     rax, [rcx]
0x18001062e  mov     rax, [rax+40h]
0x180010632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010637  mov     ebx, eax
0x180010639  test    eax, eax
0x18001063b  js      loc_18001079A
0x180010641  mov     rcx, [rsp+2D0h+String1]; String1
0x180010646  mov     rdx, r15; String2
0x180010649  call    cs:__imp__wcsicmp
0x18001064f  test    eax, eax
0x180010651  jnz     loc_180010762
0x180010657  mov     rcx, [rsp+2D0h+var_2A0]
0x18001065c  lea     r8, [rsp+2D0h+var_278]
0x180010661  xor     r9d, r9d
0x180010664  mov     [rsp+2D0h+var_2B0], rdi
0x180010669  lea     rdx, aBindinginforma; "bindingInformation"
0x180010670  mov     rax, [rcx]
0x180010673  mov     rax, [rax+40h]
0x180010677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001067c  mov     ebx, eax
0x18001067e  test    eax, eax
0x180010680  js      loc_18001079A
0x180010686  lea     eax, [rdi+5Bh]
0x180010689  mov     rbx, rsi
0x18001068c  cmp     [rsi], ax
0x18001068f  jnz     short loc_1800106A3
0x180010691  test    ax, ax
0x180010694  jz      short loc_1800106A3
0x180010696  add     rsi, 2
0x18001069a  movzx   eax, word ptr [rsi]
0x18001069d  cmp     ax, 5Dh ; ']'
0x1800106a1  jnz     short loc_180010691
0x1800106a3  mov     edx, 3Ah ; ':'; Ch
0x1800106a8  mov     rcx, rsi; Str
0x1800106ab  call    cs:__imp_wcschr
0x1800106b1  mov     rdx, rbx; unsigned __int16 *
0x1800106b4  lea     rcx, [rbp+1D0h+var_238]; this
0x1800106b8  mov     rdi, rax
0x1800106bb  test    rax, rax
0x1800106be  jz      short loc_1800106E0
0x1800106c0  mov     r8, rax
0x1800106c3  sub     r8, rbx
0x1800106c6  sar     r8, 1; unsigned int
0x1800106c9  call    ?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800106ce  mov     ebx, eax
0x1800106d0  test    eax, eax
0x1800106d2  js      loc_18001079A
0x1800106d8  lea     rdx, [rdi+2]
0x1800106dc  xor     edi, edi
0x1800106de  jmp     short loc_180010729
0x1800106e0  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800106e5  xor     edi, edi
0x1800106e7  mov     ebx, eax
0x1800106e9  test    eax, eax
0x1800106eb  js      loc_18001079A
0x1800106f1  lea     rdx, aHttp; "http"
0x1800106f8  mov     rcx, r15; String1
0x1800106fb  call    cs:__imp__wcsicmp
0x180010701  test    eax, eax
0x180010703  jnz     short loc_18001070E
0x180010705  lea     rdx, a80; "80"
0x18001070c  jmp     short loc_180010729
0x18001070e  lea     rdx, aHttps; "https"
0x180010715  mov     rcx, r15; String1
0x180010718  call    cs:__imp__wcsicmp
0x18001071e  test    eax, eax
0x180010720  jnz     short loc_18001073D
0x180010722  lea     rdx, a443; "443"
0x180010729  lea     rcx, [rsp+2D0h+var_270]; this
0x18001072e  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180010733  mov     ebx, eax
0x180010735  test    eax, eax
0x180010737  js      short loc_18001079A
0x180010739  mov     r13, [rbp+1D0h+var_250]
0x18001073d  mov     r8, [rbp+1D0h+var_218]; unsigned __int16 *
0x180010741  lea     rax, [rsp+2D0h+var_28C]
0x180010746  mov     rdx, [rsp+2D0h+var_278]; unsigned __int16 *
0x18001074b  mov     r9, r13; unsigned __int16 *
0x18001074e  mov     [rsp+2D0h+var_2B0], rax; int *
0x180010753  mov     [rsp+2D0h+var_28C], edi
0x180010757  call    ?BindingInformationMatch@SITE_OBJECT@@AEAAJPEBG00PEAH@Z; SITE_OBJECT::BindingInformationMatch(ushort const *,ushort const *,ushort const *,int *)
0x18001075c  cmp     [rsp+2D0h+var_28C], edi
0x180010760  jnz     short loc_180010780
0x180010762  mov     rcx, [rsp+2D0h+var_2A0]
0x180010767  mov     rax, [rcx]
0x18001076a  mov     rax, [rax+10h]
0x18001076e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010773  inc     r14d
0x180010776  mov     [rsp+2D0h+var_2A0], rdi
0x18001077b  jmp     loc_1800105E2
0x180010780  mov     rdi, [rsp+2D0h+var_2A0]
0x180010785  mov     dword ptr [r12], 1
0x18001078d  mov     rsi, [rsp+2D0h+var_298]
0x180010792  xor     r15d, r15d
0x180010795  mov     ebx, r15d
0x180010798  jmp     short loc_1800107AE
0x18001079a  xor     r15d, r15d
0x18001079d  mov     rsi, [rsp+2D0h+var_298]
0x1800107a2  mov     rdi, [rsp+2D0h+var_2A0]
0x1800107a7  jmp     short loc_1800107AE
0x1800107a9  mov     ebx, 80070057h
0x1800107ae  test    rdi, rdi
0x1800107b1  jz      short loc_1800107CC
0x1800107b3  mov     rax, [rdi]
0x1800107b6  mov     rcx, rdi
0x1800107b9  mov     rax, [rax+10h]
0x1800107bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107c2  mov     rsi, [rsp+2D0h+var_298]
0x1800107c7  mov     [rsp+2D0h+var_2A0], r15
0x1800107cc  test    rsi, rsi
0x1800107cf  jz      short loc_1800107E5
0x1800107d1  mov     rax, [rsi]
0x1800107d4  mov     rcx, rsi
0x1800107d7  mov     rax, [rax+10h]
0x1800107db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107e0  mov     [rsp+2D0h+var_298], r15
0x1800107e5  mov     rcx, [rsp+2D0h+var_288]
0x1800107ea  test    rcx, rcx
0x1800107ed  jz      short loc_180010800
0x1800107ef  mov     rax, [rcx]
0x1800107f2  mov     rax, [rax+10h]
0x1800107f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107fb  mov     [rsp+2D0h+var_288], r15
0x180010800  lea     rcx, [rbp+1D0h+var_200]; this
0x180010804  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180010809  lea     rcx, [rsp+2D0h+var_270]; this
0x18001080e  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180010813  lea     rcx, [rbp+1D0h+var_238]; this
0x180010817  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001081c  mov     eax, ebx
0x18001081e  mov     rcx, [rbp+1D0h+var_40]
0x180010825  xor     rcx, rsp; StackCookie
0x180010828  call    __security_check_cookie
0x18001082d  mov     rbx, [rsp+2D0h+arg_18]
0x180010835  add     rsp, 2A0h
0x18001083c  pop     r15
0x18001083e  pop     r14
0x180010840  pop     r13
0x180010842  pop     r12
0x180010844  pop     rdi
0x180010845  pop     rsi
0x180010846  pop     rbp
0x180010847  retn
```
