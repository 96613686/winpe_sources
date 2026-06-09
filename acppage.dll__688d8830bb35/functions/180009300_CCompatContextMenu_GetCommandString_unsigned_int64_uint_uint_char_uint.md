# CCompatContextMenu::GetCommandString(unsigned __int64,uint,uint *,char *,uint)

- ea: `0x180009300`
- end: `0x18000948e`
- name: `?GetCommandString@CCompatContextMenu@@UEAAJ_KIPEAIPEADI@Z`
- size: `398`
- prototype: `__int64 __fastcall(CCompatContextMenu *__hidden this, unsigned __int64, unsigned int, unsigned int *, LPWSTR lpBuffer, unsigned int cchBufferMax)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009300`

## import_xrefs

- `USER32!LoadStringA` at `0x1800093ef`
- `USER32!LoadStringA` at `0x1800093ef`
- `USER32!LoadStringW` at `0x18000934a`
- `USER32!LoadStringW` at `0x18000934a`

## pseudocode

```c
__int64 __fastcall CCompatContextMenu::GetCommandString(
        CCompatContextMenu *this,
        __int64 a2,
        int a3,
        unsigned int *a4,
        CHAR *lpBuffer,
        unsigned int cchBufferMax)
{
  int v6; // r8d
  int v7; // r8d
  int StringA; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  CHAR *v11; // r9
  const WCHAR *v12; // rax
  CHAR *v13; // rcx
  unsigned int v14; // edx
  __int64 v15; // rcx
  CHAR *v16; // r8
  const CHAR *v17; // rax
  __int64 v18; // rdx
  CHAR *v19; // rax

  if ( a2 )
    return (unsigned int)-2147024809;
  if ( a3 )
  {
    v6 = a3 - 1;
    if ( !v6 )
    {
      StringA = LoadStringA(g_hInstance, 0x7E6u, lpBuffer, cchBufferMax);
LABEL_19:
      if ( !StringA )
        return (unsigned int)-2147467259;
      return 0;
    }
    v7 = v6 - 3;
    if ( v7 )
    {
      if ( v7 != 1 )
        return 0;
      StringA = LoadStringW(g_hInstance, 0x7E6u, (LPWSTR)lpBuffer, cchBufferMax);
      goto LABEL_19;
    }
    v9 = 2147483646;
    v10 = cchBufferMax;
    if ( cchBufferMax - 1 > 0x7FFFFFFE )
    {
      v14 = -2147024809;
      if ( cchBufferMax )
        *(_WORD *)lpBuffer = 0;
    }
    else
    {
      v11 = lpBuffer;
      v12 = L"Troubleshoot";
      do
      {
        if ( !v9 )
          break;
        if ( !*v12 )
          break;
        *(_WORD *)v11 = *v12++;
        v11 += 2;
        --v9;
        --v10;
      }
      while ( v10 );
      v13 = v11 - 2;
      v14 = v10 == 0 ? 0x8007007A : 0;
      if ( v10 )
        v13 = v11;
      *(_WORD *)v13 = 0;
      if ( v10 )
        return 0;
    }
  }
  else
  {
    v15 = cchBufferMax;
    if ( !cchBufferMax )
      return (unsigned int)-2147024809;
    if ( cchBufferMax > 0x7FFFFFFFuLL )
    {
      v14 = -2147024809;
      *lpBuffer = 0;
      return v14;
    }
    v16 = lpBuffer;
    v17 = "Troubleshoot";
    v18 = 2147483646;
    do
    {
      if ( !v18 )
        break;
      if ( !*v17 )
        break;
      *v16++ = *v17++;
      --v18;
      --v15;
    }
    while ( v15 );
    v19 = v16 - 1;
    v14 = v15 == 0 ? 0x8007007A : 0;
    if ( v15 )
      v19 = v16;
    *v19 = 0;
    if ( v15 )
      return 0;
  }
  return v14;
}

```

## disassembly

```asm
0x180009300  push    rbx
0x180009302  sub     rsp, 20h
0x180009306  xor     ebx, ebx
0x180009308  test    rdx, rdx
0x18000930b  jnz     loc_180009481
0x180009311  test    r8d, r8d
0x180009314  jz      loc_180009403
0x18000931a  sub     r8d, 1
0x18000931e  jz      loc_1800093D9
0x180009324  sub     r8d, 3
0x180009328  jz      short loc_180009355
0x18000932a  cmp     r8d, 1
0x18000932e  jnz     loc_18000946B
0x180009334  mov     r9d, [rsp+28h+cchBufferMax]; cchBufferMax
0x180009339  mov     edx, 7E6h; uID
0x18000933e  mov     r8, [rsp+28h+lpBuffer]; lpBuffer
0x180009343  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18000934a  call    cs:__imp_LoadStringW
0x180009350  jmp     loc_1800093F5
0x180009355  mov     eax, [rsp+28h+cchBufferMax]
0x180009359  mov     edx, 7FFFFFFEh
0x18000935e  mov     r8d, eax
0x180009361  dec     eax
0x180009363  cmp     eax, edx
0x180009365  ja      short loc_1800093BE
0x180009367  mov     r9, [rsp+28h+lpBuffer]
0x18000936c  lea     rax, psz2; "Troubleshoot"
0x180009373  test    rdx, rdx
0x180009376  jz      short loc_180009395
0x180009378  movzx   ecx, word ptr [rax]
0x18000937b  test    cx, cx
0x18000937e  jz      short loc_180009395
0x180009380  mov     [r9], cx
0x180009384  add     rax, 2
0x180009388  add     r9, 2
0x18000938c  dec     rdx
0x18000938f  sub     r8, 1
0x180009393  jnz     short loc_180009373
0x180009395  mov     rax, r8
0x180009398  lea     rcx, [r9-2]
0x18000939c  neg     rax
0x18000939f  sbb     edx, edx
0x1800093a1  not     edx
0x1800093a3  and     edx, 8007007Ah
0x1800093a9  test    r8, r8
0x1800093ac  cmovnz  rcx, r9
0x1800093b0  mov     [rcx], bx
0x1800093b3  jnz     loc_18000946B
0x1800093b9  jmp     loc_180009486
0x1800093be  mov     edx, 80070057h
0x1800093c3  test    r8, r8
0x1800093c6  jz      loc_180009486
0x1800093cc  mov     rax, [rsp+28h+lpBuffer]
0x1800093d1  mov     [rax], bx
0x1800093d4  jmp     loc_180009486
0x1800093d9  mov     r9d, [rsp+28h+cchBufferMax]; cchBufferMax
0x1800093de  mov     edx, 7E6h; uID
0x1800093e3  mov     r8, [rsp+28h+lpBuffer]; lpBuffer
0x1800093e8  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800093ef  call    cs:__imp_LoadStringA
0x1800093f5  test    eax, eax
0x1800093f7  jnz     short loc_18000946B
0x1800093f9  mov     edx, 80004005h
0x1800093fe  jmp     loc_180009486
0x180009403  mov     eax, [rsp+28h+cchBufferMax]
0x180009407  mov     ecx, eax
0x180009409  test    eax, eax
0x18000940b  jz      short loc_18000946F
0x18000940d  cmp     rax, 7FFFFFFFh
0x180009413  jbe     short loc_18000941C
0x180009415  mov     edx, 80070057h
0x18000941a  jmp     short loc_180009478
0x18000941c  mov     r8, [rsp+28h+lpBuffer]
0x180009421  lea     rax, String2; "Troubleshoot"
0x180009428  mov     edx, 7FFFFFFEh
0x18000942d  test    rdx, rdx
0x180009430  jz      short loc_18000944C
0x180009432  mov     r9b, [rax]
0x180009435  test    r9b, r9b
0x180009438  jz      short loc_18000944C
0x18000943a  mov     [r8], r9b
0x18000943d  inc     rax
0x180009440  inc     r8
0x180009443  dec     rdx
0x180009446  sub     rcx, 1
0x18000944a  jnz     short loc_18000942D
0x18000944c  mov     rax, rcx
0x18000944f  neg     rax
0x180009452  lea     rax, [r8-1]
0x180009456  sbb     edx, edx
0x180009458  not     edx
0x18000945a  and     edx, 8007007Ah
0x180009460  test    rcx, rcx
0x180009463  cmovnz  rax, r8
0x180009467  mov     [rax], bl
0x180009469  jz      short loc_180009486
0x18000946b  mov     edx, ebx
0x18000946d  jmp     short loc_180009486
0x18000946f  mov     edx, 80070057h
0x180009474  test    eax, eax
0x180009476  jz      short loc_180009486
0x180009478  mov     rax, [rsp+28h+lpBuffer]
0x18000947d  mov     [rax], bl
0x18000947f  jmp     short loc_180009486
0x180009481  mov     edx, 80070057h
0x180009486  mov     eax, edx
0x180009488  add     rsp, 20h
0x18000948c  pop     rbx
0x18000948d  retn
```
