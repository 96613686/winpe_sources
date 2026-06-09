# BCryptGetProperty

- ea: `0x1800066f0`
- end: `0x180006bbc`
- name: `BCryptGetProperty`
- size: `1228`
- prototype: `NTSTATUS __stdcall(BCRYPT_HANDLE hObject, LPCWSTR pszProperty, PUCHAR pbOutput, ULONG cbOutput, ULONG *pcbResult, ULONG dwFlags)`
- caller_count: `13`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800049a0`
- `0x180005bc0`
- `0x180005f50`
- `0x180006020`
- `0x1800090a0`
- `0x18000bba0`
- `0x18000c1e0`
- `0x1800101c0`
- `0x180013fd4`
- `0x180014084`
- `0x180014d6c`
- `0x180016b60`
- `0x180017420`

## callees

- `0x180005060`
- `0x1800066f0`
- `0x180006bd0`
- `0x180007a7c`
- `0x18000f5bc`
- `0x18001b7b5`
- `0x18001c010`

## string_xrefs

- `0x180006995`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800069cb`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180006b0d`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180006b57`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptGetProperty(
        BCRYPT_HANDLE hObject,
        LPCWSTR pszProperty,
        PUCHAR pbOutput,
        ULONG cbOutput,
        ULONG *pcbResult,
        ULONG dwFlags)
{
  _QWORD *v10; // rcx
  __int64 v11; // rax
  int v12; // edx
  int v13; // r8d
  __int64 v14; // r13
  __int64 v15; // rsi
  __int64 v16; // rbx
  __int64 v17; // rcx
  int v18; // edx
  __int64 i; // rcx
  int v20; // edx
  int v21; // eax
  int v22; // r14d
  int v23; // ebp
  __int64 j; // rcx
  int v25; // edx
  int v26; // edx
  int v27; // esi
  int v28; // r8d
  int v29; // ecx
  ULONG v31; // ebx
  int v32; // ecx
  int v33; // eax

  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_qSqdqD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)&WPP_GLOBAL_Control,
      (_DWORD)pbOutput,
      (_DWORD)hObject,
      (__int64)pszProperty,
      (char)pbOutput,
      cbOutput,
      (char)pcbResult,
      dwFlags);
    v10 = WPP_GLOBAL_Control;
  }
  if ( pszProperty && *pszProperty && pcbResult )
  {
    v11 = ValidateBaseAlgHandle(hObject);
    v14 = v11;
    if ( v11 )
    {
      v15 = *(_QWORD *)(v11 + 24);
    }
    else
    {
      if ( ((unsigned __int8)hObject & 0xF) == 1
        || !hObject
        || *(_DWORD *)hObject < 0x18u
        || (unsigned int)(*((_DWORD *)hObject + 1) - 1431655762) > 2 )
      {
        v27 = -1073741816;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v12,
            v13,
            (unsigned int)"Status",
            8,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
            156);
        return v27;
      }
      v14 = *((_QWORD *)hObject + 1);
      v15 = *((_QWORD *)hObject + 2);
    }
    v16 = -1;
    v17 = -1;
    do
    {
      v18 = pszProperty[v17 + 1] - aProviderhandle[v17 + 1];
      if ( v18 )
        break;
      v17 += 2;
      if ( v17 == 15 )
        break;
      v18 = pszProperty[v17] - aProviderhandle[v17];
    }
    while ( !v18 );
    if ( !v18 )
    {
      *pcbResult = 8;
      if ( !pbOutput )
        return 0;
      if ( cbOutput >= 8 )
      {
        *(_QWORD *)pbOutput = v14;
        return 0;
      }
      return -1073741789;
    }
    for ( i = 0; i != 14; i += 2 )
    {
      v20 = pszProperty[i] - aPrimitivetype[i];
      if ( v20 )
        break;
      v20 = pszProperty[i + 1] - aPrimitivetype[i + 1];
      if ( v20 )
        break;
    }
    if ( !v20 )
    {
      *pcbResult = 4;
      if ( !pbOutput )
        return 0;
      if ( cbOutput >= 4 )
      {
        v27 = 0;
        *(_DWORD *)pbOutput = *(_DWORD *)(v14 + 36);
        return v27;
      }
      return -1073741789;
    }
    v21 = *(_DWORD *)(v14 + 36);
    v22 = 0;
    if ( v21 == 1 )
    {
LABEL_18:
      v23 = 32;
LABEL_19:
      for ( j = 0; j != 12; j += 2 )
      {
        v25 = pszProperty[j] - aIskeyedhash[j];
        if ( v25 )
          break;
        v25 = pszProperty[j + 1] - aIskeyedhash[j + 1];
        if ( v25 )
          break;
      }
      if ( !v25 && v22 )
      {
        *pcbResult = 4;
        if ( pbOutput )
        {
          if ( cbOutput >= 4 )
          {
            *(_DWORD *)pbOutput = 1;
            return 0;
          }
          return -1073741789;
        }
        return 0;
      }
      v27 = (*(__int64 (__fastcall **)(__int64, LPCWSTR, PUCHAR, _QWORD, ULONG *, ULONG))(v14 + 64))(
              v15,
              pszProperty,
              pbOutput,
              cbOutput,
              pcbResult,
              dwFlags);
      if ( v27 >= 0 )
      {
        do
        {
          v29 = pszProperty[v16 + 1] - aObjectlength[v16 + 1];
          if ( v29 )
            break;
          v16 += 2;
          if ( v16 == 13 )
            break;
          v29 = pszProperty[v16] - aObjectlength[v16];
        }
        while ( !v29 );
        if ( v29 )
        {
          v31 = cbOutput;
        }
        else
        {
          *pcbResult = 4;
          if ( !pbOutput )
            return 0;
          v31 = cbOutput;
          if ( cbOutput < 4 )
            return -1073741789;
          v32 = *(_DWORD *)pbOutput;
          if ( v22 )
            v33 = v23 + *(_DWORD *)(v14 + 12) + 2 * v32 + 15;
          else
            v33 = v32 + v23;
          *(_DWORD *)pbOutput = v33 + 30;
        }
        if ( wcscmp_0(pszProperty, L"MultiObjectLength") )
          return 0;
        *pcbResult = 8;
        if ( !pbOutput )
          return 0;
        if ( v31 >= 8 )
        {
          *(_DWORD *)pbOutput += v23 + 30;
          return 0;
        }
        return -1073741789;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v26,
          v28,
          (unsigned int)"Status",
          v27,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
          41);
    }
    else
    {
      switch ( v21 )
      {
        case 2:
          v23 = 40;
          v22 = (*(_DWORD *)(v14 + 8) >> 3) & 1;
          goto LABEL_19;
        case 3:
        case 4:
        case 5:
        case 7:
        case 8:
          goto LABEL_18;
        case 6:
          v23 = 0;
          goto LABEL_19;
        default:
          v27 = -1073741816;
          DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
          break;
      }
    }
  }
  else
  {
    v27 = -1073741811;
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        v10[2],
        (unsigned int)&WPP_GLOBAL_Control,
        (_DWORD)pbOutput,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        138);
  }
  return v27;
}

```

## disassembly

```asm
0x1800066f0  mov     [rsp+arg_18], r9d
0x1800066f5  mov     [rsp+arg_10], r8
0x1800066fa  push    rbx
0x1800066fb  push    rbp
0x1800066fc  push    rsi
0x1800066fd  push    rdi
0x1800066fe  push    r12
0x180006700  push    r14
0x180006702  push    r15
0x180006704  sub     rsp, 50h
0x180006708  mov     ebp, r9d
0x18000670b  mov     r14, r8
0x18000670e  mov     rdi, rdx
0x180006711  mov     rbx, rcx
0x180006714  mov     rcx, cs:WPP_GLOBAL_Control
0x18000671b  lea     rdx, WPP_GLOBAL_Control
0x180006722  mov     r15d, [rsp+88h+dwFlags]
0x18000672a  mov     r12, [rsp+88h+pcbResult]
0x180006732  cmp     rcx, rdx
0x180006735  jnz     loc_1800068F9
0x18000673b  mov     [rsp+88h+arg_0], r13
0x180006743  test    rdi, rdi
0x180006746  jz      loc_1800069AB
0x18000674c  xor     eax, eax
0x18000674e  cmp     ax, [rdi]
0x180006751  jz      loc_1800069AB
0x180006757  test    r12, r12
0x18000675a  jz      loc_1800069AB
0x180006760  mov     rcx, rbx
0x180006763  call    ValidateBaseAlgHandle
0x180006768  mov     r13, rax
0x18000676b  test    rax, rax
0x18000676e  jz      loc_18000693A
0x180006774  mov     rsi, [rax+18h]
0x180006778  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000677f  lea     r8, aProviderhandle; "ProviderHandle"
0x180006786  mov     rcx, rbx
0x180006789  nop     dword ptr [rax+00000000h]
0x180006790  movzx   edx, word ptr [rdi+rcx*2+2]
0x180006795  movzx   eax, word ptr [r8+rcx*2+2]
0x18000679b  sub     edx, eax
0x18000679d  jnz     short loc_1800067B6
0x18000679f  add     rcx, 2
0x1800067a3  cmp     rcx, 0Fh
0x1800067a7  jz      short loc_1800067B6
0x1800067a9  movzx   edx, word ptr [rdi+rcx*2]
0x1800067ad  movzx   eax, word ptr [r8+rcx*2]
0x1800067b2  sub     edx, eax
0x1800067b4  jz      short loc_180006790
0x1800067b6  test    edx, edx
0x1800067b8  jz      loc_180006A89
0x1800067be  lea     r8, aPrimitivetype; "PrimitiveType"
0x1800067c5  xor     ecx, ecx
0x1800067c7  nop     word ptr [rax+rax+00000000h]
0x1800067d0  movzx   edx, word ptr [rdi+rcx*2]
0x1800067d4  movzx   eax, word ptr [r8+rcx*2]
0x1800067d9  sub     edx, eax
0x1800067db  jnz     short loc_1800067F6
0x1800067dd  movzx   edx, word ptr [rdi+rcx*2+2]
0x1800067e2  movzx   eax, word ptr [r8+rcx*2+2]
0x1800067e8  sub     edx, eax
0x1800067ea  jnz     short loc_1800067F6
0x1800067ec  add     rcx, 2
0x1800067f0  cmp     rcx, 0Eh
0x1800067f4  jnz     short loc_1800067D0
0x1800067f6  test    edx, edx
0x1800067f8  jz      loc_180006B22
0x1800067fe  mov     eax, [r13+24h]
0x180006802  xor     r14d, r14d
0x180006805  cmp     eax, 1
0x180006808  jnz     loc_180006A50
0x18000680e  mov     ebp, 20h ; ' '; jumptable 0000000180006A6D cases 3-5,7,8
0x180006813  mov     r10d, 40h ; '@'
0x180006819  lea     r8, aIskeyedhash; "IsKeyedHash"
0x180006820  mov     r11, r13
0x180006823  xor     ecx, ecx
0x180006825  nop     word ptr [rax+rax+00000000h]
0x180006830  movzx   edx, word ptr [rdi+rcx*2]
0x180006834  movzx   eax, word ptr [r8+rcx*2]
0x180006839  sub     edx, eax
0x18000683b  jnz     short loc_180006856
0x18000683d  movzx   edx, word ptr [rdi+rcx*2+2]
0x180006842  movzx   eax, word ptr [r8+rcx*2+2]
0x180006848  sub     edx, eax
0x18000684a  jnz     short loc_180006856
0x18000684c  add     rcx, 2
0x180006850  cmp     rcx, 0Ch
0x180006854  jnz     short loc_180006830
0x180006856  test    edx, edx
0x180006858  jz      loc_180006AA7
0x18000685e  mov     r9d, [rsp+88h+arg_18]
0x180006866  mov     rdx, rdi
0x180006869  mov     rax, [r11+r10]
0x18000686d  mov     rcx, rsi
0x180006870  mov     dword ptr [rsp+88h+var_60], r15d
0x180006875  mov     r15, [rsp+88h+arg_10]
0x18000687d  mov     r8, r15
0x180006880  mov     [rsp+88h+var_68], r12
0x180006885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000688a  mov     esi, eax
0x18000688c  test    eax, eax
0x18000688e  js      loc_180006AE4
0x180006894  lea     rdx, aObjectlength; "ObjectLength"
0x18000689b  nop     dword ptr [rax+rax+00h]
0x1800068a0  movzx   ecx, word ptr [rdi+rbx*2+2]
0x1800068a5  movzx   eax, word ptr [rdx+rbx*2+2]
0x1800068aa  sub     ecx, eax
0x1800068ac  jnz     short loc_1800068C4
0x1800068ae  add     rbx, 2
0x1800068b2  cmp     rbx, 0Dh
0x1800068b6  jz      short loc_1800068C4
0x1800068b8  movzx   ecx, word ptr [rdi+rbx*2]
0x1800068bc  movzx   eax, word ptr [rdx+rbx*2]
0x1800068c0  sub     ecx, eax
0x1800068c2  jz      short loc_1800068A0
0x1800068c4  test    ecx, ecx
0x1800068c6  jnz     loc_180006A39
0x1800068cc  mov     dword ptr [r12], 4
0x1800068d4  test    r15, r15
0x1800068d7  jnz     loc_1800069F4
0x1800068dd  xor     esi, esi
0x1800068df  mov     r13, [rsp+88h+arg_0]
0x1800068e7  mov     eax, esi
0x1800068e9  add     rsp, 50h
0x1800068ed  pop     r15
0x1800068ef  pop     r14
0x1800068f1  pop     r12
0x1800068f3  pop     rdi
0x1800068f4  pop     rsi
0x1800068f5  pop     rbp
0x1800068f6  pop     rbx
0x1800068f7  retn
0x1800068f9  test    byte ptr [rcx+1Ch], 4
0x1800068fd  jz      loc_18000673B
0x180006903  mov     rcx, [rcx+10h]
0x180006907  mov     r9, rbx
0x18000690a  mov     [rsp+88h+var_48], r15d
0x18000690f  mov     [rsp+88h+var_50], r12
0x180006914  mov     [rsp+88h+var_58], ebp
0x180006918  mov     [rsp+88h+var_60], r14
0x18000691d  mov     [rsp+88h+var_68], rdi
0x180006922  call    WPP_SF_qSqdqD
0x180006927  mov     rcx, cs:WPP_GLOBAL_Control
0x18000692e  lea     rdx, WPP_GLOBAL_Control
0x180006935  jmp     loc_18000673B
0x18000693a  movzx   eax, bl
0x18000693d  and     al, 0Fh
0x18000693f  cmp     al, 1
0x180006941  jz      short loc_180006967
0x180006943  test    rbx, rbx
0x180006946  jz      short loc_180006967
0x180006948  cmp     dword ptr [rbx], 18h
0x18000694b  jb      short loc_180006967
0x18000694d  mov     eax, [rbx+4]
0x180006950  sub     eax, 55555552h
0x180006955  cmp     eax, 2
0x180006958  ja      short loc_180006967
0x18000695a  mov     r13, [rbx+8]
0x18000695e  mov     rsi, [rbx+10h]
0x180006962  jmp     loc_180006778
0x180006967  mov     esi, 0C0000008h
0x18000696c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006973  lea     rax, WPP_GLOBAL_Control
0x18000697a  cmp     rcx, rax
0x18000697d  jz      loc_1800068DF
0x180006983  test    byte ptr [rcx+1Ch], 1
0x180006987  jz      loc_1800068DF
0x18000698d  mov     [rsp+88h+var_58], 0B9Ch
0x180006995  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000699c  mov     [rsp+88h+var_60], rax
0x1800069a1  mov     dword ptr [rsp+88h+var_68], 0C0000008h
0x1800069a9  jmp     short loc_1800069DF
0x1800069ab  mov     esi, 0C000000Dh
0x1800069b0  cmp     rcx, rdx
0x1800069b3  jz      loc_1800068DF
0x1800069b9  test    byte ptr [rcx+1Ch], 1
0x1800069bd  jz      loc_1800068DF
0x1800069c3  mov     [rsp+88h+var_58], 0B8Ah
0x1800069cb  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800069d2  mov     [rsp+88h+var_60], rax
0x1800069d7  mov     dword ptr [rsp+88h+var_68], 0C000000Dh
0x1800069df  mov     rcx, [rcx+10h]
0x1800069e3  lea     r9, aStatus; "Status"
0x1800069ea  call    WPP_SF_sDsd
0x1800069ef  jmp     loc_1800068DF
0x1800069f4  mov     ebx, [rsp+88h+arg_18]
0x1800069fb  cmp     ebx, 4
0x1800069fe  jb      short loc_180006A2F
0x180006a00  mov     ecx, [r15]
0x180006a03  test    r14d, r14d
0x180006a06  jnz     short loc_180006A42
0x180006a08  lea     eax, [rcx+rbp]
0x180006a0b  add     eax, 1Eh
0x180006a0e  mov     [r15], eax
0x180006a11  lea     rdx, aMultiobjectlen; "MultiObjectLength"
0x180006a18  mov     rcx, rdi; String1
0x180006a1b  call    wcscmp_0
0x180006a20  test    eax, eax
0x180006a22  jz      loc_180006B79
0x180006a28  xor     esi, esi
0x180006a2a  jmp     loc_1800068DF
0x180006a2f  mov     esi, 0C0000023h
0x180006a34  jmp     loc_1800068DF
0x180006a39  mov     ebx, [rsp+88h+arg_18]
0x180006a40  jmp     short loc_180006A11
0x180006a42  mov     eax, [r13+0Ch]
0x180006a46  lea     eax, [rax+rcx*2]
0x180006a49  add     eax, 0Fh
0x180006a4c  add     eax, ebp
0x180006a4e  jmp     short loc_180006A0B
0x180006a50  add     eax, 0FFFFFFFEh; switch 7 cases
0x180006a53  cmp     eax, 6
0x180006a56  ja      def_180006A6D; jumptable 0000000180006A6D default case
0x180006a5c  lea     rcx, __ImageBase
0x180006a63  mov     eax, ds:(jpt_180006A6D - 180000000h)[rcx+rax*4]
0x180006a6a  add     rax, rcx
0x180006a6d  jmp     rax; switch jump
0x180006a73  mov     r14d, [r13+8]; jumptable 0000000180006A6D case 2
0x180006a77  mov     ebp, 28h ; '('
0x180006a7c  shr     r14d, 3
0x180006a80  and     r14d, 1
0x180006a84  jmp     loc_180006813
0x180006a89  mov     dword ptr [r12], 8
0x180006a91  test    r14, r14
0x180006a94  jz      loc_1800068DD
0x180006a9a  cmp     ebp, 8
0x180006a9d  jb      short loc_180006A2F
0x180006a9f  mov     [r14], r13
0x180006aa2  jmp     loc_1800068DD
0x180006aa7  test    r14d, r14d
0x180006aaa  jz      loc_18000685E
0x180006ab0  mov     rax, [rsp+88h+arg_10]
0x180006ab8  mov     dword ptr [r12], 4
0x180006ac0  test    rax, rax
0x180006ac3  jz      loc_1800068DD
0x180006ac9  cmp     [rsp+88h+arg_18], 4
0x180006ad1  jb      loc_180006A2F
0x180006ad7  mov     dword ptr [rax], 1
0x180006add  xor     esi, esi
0x180006adf  jmp     loc_1800068DF
0x180006ae4  mov     rcx, cs:WPP_GLOBAL_Control
0x180006aeb  lea     rax, WPP_GLOBAL_Control
0x180006af2  cmp     rcx, rax
0x180006af5  jz      loc_1800068DF
0x180006afb  test    byte ptr [rcx+1Ch], 1
0x180006aff  jz      loc_1800068DF
0x180006b05  mov     [rsp+88h+var_58], 0C29h
0x180006b0d  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006b14  mov     [rsp+88h+var_60], rax
0x180006b19  mov     dword ptr [rsp+88h+var_68], esi
0x180006b1d  jmp     loc_1800069DF
0x180006b22  mov     dword ptr [r12], 4
0x180006b2a  test    r14, r14
0x180006b2d  jz      loc_1800068DD
0x180006b33  cmp     ebp, 4
0x180006b36  jb      loc_180006A2F
0x180006b3c  mov     eax, [r13+24h]
0x180006b40  xor     esi, esi
0x180006b42  mov     [r14], eax
0x180006b45  jmp     loc_1800068DF
0x180006b4a  xor     ebp, ebp; jumptable 0000000180006A6D case 6
0x180006b4c  jmp     loc_180006813
0x180006b51  mov     r9d, 0C01h; jumptable 0000000180006A6D default case
0x180006b57  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006b5e  lea     rdx, aStatus; "Status"
0x180006b65  mov     ecx, 0C0000008h
0x180006b6a  mov     esi, 0C0000008h
0x180006b6f  call    DebugTraceError
0x180006b74  jmp     loc_1800068DF
0x180006b79  mov     dword ptr [r12], 8
0x180006b81  test    r15, r15
0x180006b84  jz      loc_1800068DD
0x180006b8a  cmp     ebx, 8
0x180006b8d  jb      loc_180006A2F
0x180006b93  lea     eax, [rbp+1Eh]
0x180006b96  add     [r15], eax
0x180006b99  jmp     loc_180006A28
```
