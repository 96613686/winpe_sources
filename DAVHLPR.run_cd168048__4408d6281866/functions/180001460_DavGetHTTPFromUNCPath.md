# DavGetHTTPFromUNCPath

- ea: `0x180001460`
- end: `0x180001829`
- name: `DavGetHTTPFromUNCPath`
- size: `969`
- prototype: `DWORD __stdcall(LPCWSTR UncPath, LPWSTR Url, LPDWORD lpSize)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180001460`
- `0x180001830`
- `0x180001ba0`
- `0x180003570`
- `0x180004850`

## import_xrefs

- `msvcrt!wcscspn` at `0x180001550`
- `msvcrt!wcscspn` at `0x180001550`
- `msvcrt!_wcsnicmp` at `0x180001585`
- `msvcrt!_wcsnicmp` at `0x1800016d5`
- `msvcrt!_wcsnicmp` at `0x180001585`
- `msvcrt!_wcsnicmp` at `0x1800016d5`
- `KERNEL32!LocalFree` at `0x1800016a5`
- `KERNEL32!LocalFree` at `0x18000181e`
- `KERNEL32!LocalFree` at `0x1800016a5`
- `KERNEL32!LocalFree` at `0x18000181e`
- `KERNEL32!GetLastError` at `0x1800017bb`
- `KERNEL32!GetLastError` at `0x1800017bb`
- `KERNEL32!LocalAlloc` at `0x180001652`
- `KERNEL32!LocalAlloc` at `0x180001652`

## pseudocode

```c
DWORD __stdcall DavGetHTTPFromUNCPath(LPCWSTR UncPath, LPWSTR Url, LPDWORD lpSize)
{
  DWORD LastError; // ebx
  int v7; // eax
  wchar_t *v8; // r12
  int v9; // eax
  wchar_t *v10; // rbx
  size_t v11; // rax
  wchar_t *v12; // rdi
  char v13; // r13
  wchar_t v14; // ax
  __int64 v15; // rax
  wchar_t *v17; // r14
  __int64 v18; // r14
  HLOCAL v19; // rax
  unsigned __int64 v20; // rcx
  __int64 v21; // rdx
  __int16 v22; // ax
  wchar_t *v23; // rax
  DWORD v24; // eax
  _OWORD v25[3]; // [rsp+28h] [rbp-89h] BYREF
  __int128 v26[3]; // [rsp+58h] [rbp-59h] BYREF
  __int128 v27; // [rsp+88h] [rbp-29h]
  HLOCAL hMem[2]; // [rsp+98h] [rbp-19h]
  __int128 v29; // [rsp+A8h] [rbp-9h]
  __int128 v30; // [rsp+B8h] [rbp+7h]
  __int64 v31; // [rsp+C8h] [rbp+17h]
  wchar_t *String; // [rsp+118h] [rbp+67h] BYREF
  __int64 v33; // [rsp+130h] [rbp+7Fh]

  String = 0;
  v31 = 0;
  memset(v26, 0, sizeof(v26));
  v27 = 0;
  *(_OWORD *)hMem = 0;
  v29 = 0;
  v30 = 0;
  if ( !UncPath || !lpSize || *lpSize && !Url )
  {
    LastError = 87;
    goto LABEL_3;
  }
  v7 = DavCanonicalizeUncPathAndDetermineType(UncPath, &String, 0);
  v8 = String;
  if ( v7 )
  {
    memset(v25, 0, 32);
    v9 = 2;
    v10 = String;
    while ( v9 )
    {
      if ( *v10 != 92 && *v10 != 47 )
        goto LABEL_44;
      ++v10;
      --v9;
    }
    *((_QWORD *)&v25[0] + 1) = v10;
    v11 = wcscspn(v10, L"@\\/");
    v12 = &v10[v11];
    *(_QWORD *)&v25[1] = &v10[v11];
    if ( (__int64)((v11 * 2) & 0xFFFFFFFFFFFFFFFEuLL) < 2 )
    {
      LastError = 87;
      goto LABEL_26;
    }
    v13 = v25[0];
    if ( !_wcsnicmp(v12, L"@SSL", 4u) )
    {
      v13 = LOBYTE(v25[0]) | 1;
      LOBYTE(v25[0]) |= 1u;
      v12 += 4;
    }
    v14 = *v12;
    if ( *v12 == 64 )
    {
      String = v12 + 1;
      LastError = DavpParseUInt16(&String, (char *)v25 + 4);
      if ( LastError )
        goto LABEL_26;
      v12 = String;
      v14 = *String;
      if ( *String && v14 != 92 && v14 != 47 )
      {
LABEL_44:
        LastError = 87;
        goto LABEL_26;
      }
      v13 = LOBYTE(v25[0]) | 2;
    }
    if ( (v14 == 47 || v14 == 92) && !_wcsnicmp(v12 + 1, L"DavWWWRoot", 0xAu) )
    {
      if ( (v20 = v12[11], (unsigned int)v20 <= 0x3A) && (v21 = 0x400800000000001LL, _bittest64(&v21, v20))
        || (_DWORD)v20 == 92 )
      {
        v12 += 11;
      }
    }
    v15 = -1;
    while ( v12[++v15] != 0 )
      ;
    *(_QWORD *)&v26[0] = L"https";
    v27 = *(_OWORD *)((char *)v25 + 8);
    v17 = &v12[v15];
    *((_QWORD *)&v26[0] + 1) = &aHttps_1[(v13 & 1) + 4];
    if ( (v13 & 2) != 0 )
    {
      v22 = 443;
      if ( (v13 & 1) == 0 )
        v22 = 80;
      if ( WORD2(v25[0]) != v22 )
      {
        BYTE2(hMem[0]) = 1;
        LOWORD(hMem[0]) = WORD2(v25[0]);
      }
    }
    String = 0;
    v18 = v17 - v12;
    LastError = DavUrlEncodeNtPath(v12, v18, 0, &String);
    if ( LastError != 122 )
      goto LABEL_25;
    v33 = 0;
    if ( !is_mul_ok((unsigned __int64)String, 2u) )
      goto LABEL_26;
    v19 = LocalAlloc(0, 2LL * (_QWORD)String);
    hMem[1] = v19;
    if ( v19 )
    {
      LastError = DavUrlEncodeNtPath(v12, v18, (char *)v19, &String);
LABEL_25:
      if ( !LastError )
      {
        v23 = (wchar_t *)*lpSize;
        *(_QWORD *)&v29 = (char *)hMem[1] + 2 * (_QWORD)String;
        String = v23;
        v24 = DavCreateUrl(v26, Url, (unsigned __int64 *)&String);
        LastError = v24;
        if ( !v24 || v24 == 122 )
        {
          if ( (unsigned __int64)String > 0xFFFFFFFF )
          {
            *lpSize = -1;
            LastError = 534;
          }
          else
          {
            *lpSize = (unsigned int)String;
          }
        }
      }
      goto LABEL_26;
    }
    LastError = GetLastError();
  }
  else
  {
    LastError = 67;
  }
LABEL_26:
  if ( v8 )
    LocalFree(v8);
LABEL_3:
  if ( hMem[1] )
    LocalFree(hMem[1]);
  return LastError;
}

```

## disassembly

```asm
0x180001460  mov     rax, rsp
0x180001463  push    rbp
0x180001464  push    rbx
0x180001465  lea     rbp, [rax-5Fh]
0x180001469  sub     rsp, 0F8h
0x180001470  xorps   xmm0, xmm0
0x180001473  mov     [rax+10h], rsi
0x180001477  mov     [rax-20h], r12
0x18000147b  mov     rsi, r8
0x18000147e  mov     [rax-38h], r15
0x180001482  mov     r15, rdx
0x180001485  xor     eax, eax
0x180001487  mov     [rbp+57h+String], 0
0x18000148f  mov     [rbp+57h+var_40], rax
0x180001493  movups  [rbp+57h+var_B0], xmm0
0x180001497  movups  [rbp+57h+var_A0], xmm0
0x18000149b  movups  [rbp+57h+var_90], xmm0
0x18000149f  movups  [rbp+57h+var_80], xmm0
0x1800014a3  movups  xmmword ptr [rbp+57h+hMem], xmm0
0x1800014a7  movups  [rbp+57h+var_60], xmm0
0x1800014ab  movups  [rbp+57h+var_50], xmm0
0x1800014af  test    rcx, rcx
0x1800014b2  jnz     short loc_1800014EA
0x1800014b4  mov     ebx, 57h ; 'W'
0x1800014b9  mov     rcx, [rbp+57h+hMem+8]; Src
0x1800014bd  mov     r15, [rsp+100h+var_30]
0x1800014c5  mov     r12, [rsp+100h+var_18]
0x1800014cd  mov     rsi, [rsp+100h+arg_8]
0x1800014d5  test    rcx, rcx
0x1800014d8  jnz     loc_18000181E
0x1800014de  mov     eax, ebx
0x1800014e0  add     rsp, 0F8h
0x1800014e7  pop     rbx
0x1800014e8  pop     rbp
0x1800014e9  retn
0x1800014ea  test    rsi, rsi
0x1800014ed  jz      short loc_1800014B4
0x1800014ef  cmp     [r8], eax
0x1800014f2  jnz     loc_180001716
0x1800014f8  xor     r8d, r8d
0x1800014fb  lea     rdx, [rbp+57h+String]
0x1800014ff  call    DavCanonicalizeUncPathAndDetermineType
0x180001504  mov     r12, [rbp+57h+String]
0x180001508  test    eax, eax
0x18000150a  jz      loc_180001724
0x180001510  xorps   xmm0, xmm0
0x180001513  mov     [rsp+0F0h], rdi
0x18000151b  movups  [rsp+100h+var_E8+8], xmm0
0x180001520  mov     eax, 2
0x180001525  mov     rbx, r12
0x180001528  movups  [rbp+57h+var_D0], xmm0
0x18000152c  mov     edx, 0FFFFFFFFh
0x180001531  mov     [rsp+100h+var_20], r13
0x180001539  test    eax, eax
0x18000153b  jnz     loc_1800016B0
0x180001541  lea     rdx, Control; "@\\/"
0x180001548  mov     [rsp+28h], rbx
0x18000154d  mov     rcx, rbx; String
0x180001550  call    cs:__imp_wcscspn
0x180001556  add     rax, rax
0x180001559  lea     rdi, [rax+rbx]
0x18000155d  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001561  mov     qword ptr [rbp+57h+var_D0], rdi
0x180001565  cmp     rax, 2
0x180001569  jge     short loc_180001575
0x18000156b  mov     ebx, 57h ; 'W'
0x180001570  jmp     loc_180001689
0x180001575  mov     r8d, 4; MaxCount
0x18000157b  lea     rdx, aSsl; "@SSL"
0x180001582  mov     rcx, rdi; String1
0x180001585  call    cs:__imp__wcsnicmp
0x18000158b  mov     r13d, dword ptr [rsp+100h+var_E8+8]
0x180001590  test    eax, eax
0x180001592  jz      loc_18000172E
0x180001598  movzx   eax, word ptr [rdi]
0x18000159b  cmp     ax, 40h ; '@'
0x18000159f  jz      loc_180001740
0x1800015a5  mov     [rsp+100h+var_28], r14
0x1800015ad  cmp     ax, 2Fh ; '/'
0x1800015b1  jz      loc_1800016C4
0x1800015b7  cmp     ax, 5Ch ; '\'
0x1800015bb  jz      loc_1800016C4
0x1800015c1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800015c8  nop     dword ptr [rax+rax+00000000h]
0x1800015d0  cmp     word ptr [rdi+rax*2+2], 0
0x1800015d6  lea     rax, [rax+1]
0x1800015da  jnz     short loc_1800015D0
0x1800015dc  movups  xmm0, xmmword ptr [rsp+28h]
0x1800015e1  mov     ecx, r13d
0x1800015e4  lea     rdx, aHttps_1; "https"
0x1800015eb  and     ecx, 1
0x1800015ee  mov     qword ptr [rbp+57h+var_B0], rdx
0x1800015f2  movaps  [rbp+57h+var_80], xmm0
0x1800015f6  lea     r14, [rdi+rax*2]
0x1800015fa  lea     rax, [rdx+8]
0x1800015fe  lea     rax, [rax+rcx*2]
0x180001602  mov     qword ptr [rbp+57h+var_B0+8], rax
0x180001606  test    r13b, 2
0x18000160a  jnz     loc_180001790
0x180001610  sub     r14, rdi
0x180001613  mov     [rbp+57h+String], 0
0x18000161b  sar     r14, 1
0x18000161e  lea     r9, [rbp+57h+String]
0x180001622  mov     rdx, r14
0x180001625  xor     r8d, r8d
0x180001628  mov     rcx, rdi
0x18000162b  call    DavUrlEncodeNtPath
0x180001630  mov     ebx, eax
0x180001632  cmp     eax, 7Ah ; 'z'
0x180001635  jnz     short loc_180001679
0x180001637  mov     eax, 2
0x18000163c  mov     [rbp+57h+arg_18], 0
0x180001644  mul     [rbp+57h+String]
0x180001648  test    rdx, rdx
0x18000164b  jnz     short loc_180001681
0x18000164d  mov     rdx, rax; uBytes
0x180001650  xor     ecx, ecx; uFlags
0x180001652  call    cs:__imp_LocalAlloc
0x180001658  mov     [rbp+57h+hMem+8], rax
0x18000165c  test    rax, rax
0x18000165f  jz      loc_1800017BB
0x180001665  lea     r9, [rbp+57h+String]
0x180001669  mov     r8, rax
0x18000166c  mov     rdx, r14
0x18000166f  mov     rcx, rdi
0x180001672  call    DavUrlEncodeNtPath
0x180001677  mov     ebx, eax
0x180001679  test    ebx, ebx
0x18000167b  jz      loc_1800017C8
0x180001681  mov     r14, [rsp+100h+var_28]
0x180001689  mov     rdi, [rsp+0F0h]
0x180001691  mov     r13, [rsp+100h+var_20]
0x180001699  test    r12, r12
0x18000169c  jz      loc_1800014B9
0x1800016a2  mov     rcx, r12; hMem
0x1800016a5  call    cs:__imp_LocalFree
0x1800016ab  jmp     loc_1800014B9
0x1800016b0  movzx   ecx, word ptr [rbx]
0x1800016b3  cmp     cx, 5Ch ; '\'
0x1800016b7  jnz     short loc_18000170E
0x1800016b9  add     rbx, 2
0x1800016bd  add     eax, edx
0x1800016bf  jmp     loc_180001539
0x1800016c4  mov     r8d, 0Ah; MaxCount
0x1800016ca  lea     rdx, aDavwwwroot; "DavWWWRoot"
0x1800016d1  lea     rcx, [rdi+2]; String1
0x1800016d5  call    cs:__imp__wcsnicmp
0x1800016db  test    eax, eax
0x1800016dd  jnz     loc_1800015C1
0x1800016e3  movzx   ecx, word ptr [rdi+16h]
0x1800016e7  cmp     ecx, 3Ah ; ':'
0x1800016ea  ja      short loc_1800016FC
0x1800016ec  mov     rdx, 400800000000001h
0x1800016f6  bt      rdx, rcx
0x1800016fa  jb      short loc_180001705
0x1800016fc  cmp     ecx, 5Ch ; '\'
0x1800016ff  jnz     loc_1800015C1
0x180001705  add     rdi, 16h
0x180001709  jmp     loc_1800015C1
0x18000170e  cmp     cx, 2Fh ; '/'
0x180001712  jz      short loc_1800016B9
0x180001714  jmp     short loc_180001778
0x180001716  test    r15, r15
0x180001719  jz      loc_1800014B4
0x18000171f  jmp     loc_1800014F8
0x180001724  mov     ebx, 43h ; 'C'
0x180001729  jmp     loc_180001699
0x18000172e  or      r13d, 1
0x180001732  mov     dword ptr [rsp+100h+var_E8+8], r13d
0x180001737  add     rdi, 8
0x18000173b  jmp     loc_180001598
0x180001740  lea     rax, [rdi+2]
0x180001744  lea     rdx, [rsp+100h+var_E8+0Ch]
0x180001749  mov     [rbp+57h+String], rax
0x18000174d  lea     rcx, [rbp+57h+String]
0x180001751  call    DavpParseUInt16
0x180001756  mov     ebx, eax
0x180001758  test    eax, eax
0x18000175a  jnz     loc_180001689
0x180001760  mov     rdi, [rbp+57h+String]
0x180001764  movzx   eax, word ptr [rdi]
0x180001767  test    ax, ax
0x18000176a  jz      short loc_180001782
0x18000176c  cmp     ax, 5Ch ; '\'
0x180001770  jz      short loc_180001782
0x180001772  cmp     ax, 2Fh ; '/'
0x180001776  jz      short loc_180001782
0x180001778  mov     ebx, 57h ; 'W'
0x18000177d  jmp     loc_180001689
0x180001782  mov     r13d, dword ptr [rsp+100h+var_E8+8]
0x180001787  or      r13d, 2
0x18000178b  jmp     loc_1800015A5
0x180001790  test    ecx, ecx
0x180001792  mov     eax, 1BBh
0x180001797  movzx   ecx, word ptr [rsp+100h+var_E8+0Ch]
0x18000179c  mov     edx, 50h ; 'P'
0x1800017a1  cmovz   ax, dx
0x1800017a5  cmp     cx, ax
0x1800017a8  jz      loc_180001610
0x1800017ae  mov     byte ptr [rbp+57h+hMem+2], 1
0x1800017b2  mov     word ptr [rbp+57h+hMem], cx
0x1800017b6  jmp     loc_180001610
0x1800017bb  call    cs:__imp_GetLastError
0x1800017c1  mov     ebx, eax
0x1800017c3  jmp     loc_180001681
0x1800017c8  mov     rcx, [rbp+57h+String]
0x1800017cc  lea     r8, [rbp+57h+String]
0x1800017d0  mov     rax, [rbp+57h+hMem+8]
0x1800017d4  mov     rdx, r15
0x1800017d7  lea     rcx, [rax+rcx*2]
0x1800017db  mov     eax, [rsi]
0x1800017dd  mov     qword ptr [rbp+57h+var_60], rcx
0x1800017e1  lea     rcx, [rbp+57h+var_B0]
0x1800017e5  mov     [rbp+57h+String], rax
0x1800017e9  call    DavCreateUrl
0x1800017ee  mov     ebx, eax
0x1800017f0  test    eax, eax
0x1800017f2  jz      short loc_1800017FD
0x1800017f4  cmp     eax, 7Ah ; 'z'
0x1800017f7  jnz     loc_180001681
0x1800017fd  mov     rax, [rbp+57h+String]
0x180001801  mov     ecx, 0FFFFFFFFh
0x180001806  cmp     rax, rcx
0x180001809  ja      short loc_180001812
0x18000180b  mov     [rsi], eax
0x18000180d  jmp     loc_180001681
0x180001812  mov     [rsi], ecx
0x180001814  mov     ebx, 216h
0x180001819  jmp     loc_180001681
0x18000181e  call    cs:__imp_LocalFree
0x180001824  jmp     loc_1800014DE
```
