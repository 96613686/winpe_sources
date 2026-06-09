# importRsaPublicKey

- ea: `0x180008820`
- end: `0x180008976`
- name: `importRsaPublicKey`
- size: `342`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE hAlgorithm)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800078e4`

## callees

- `0x180008820`
- `0x18000967e`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180008891`
- `ole32!CoTaskMemAlloc` at `0x180008891`
- `ole32!CoTaskMemFree` at `0x180008956`
- `ole32!CoTaskMemFree` at `0x180008956`
- `bcrypt!BCryptImportKeyPair` at `0x18000893e`
- `bcrypt!BCryptImportKeyPair` at `0x18000893e`

## pseudocode

```c
__int64 __fastcall importRsaPublicKey(BCRYPT_ALG_HANDLE hAlgorithm, __int64 a2, BCRYPT_KEY_HANDLE *a3)
{
  int v3; // eax
  _QWORD *pbInput; // rsi
  unsigned int v6; // edi
  unsigned int v7; // edi
  unsigned int v10; // ebx
  unsigned int v11; // eax
  ULONG cbInput; // ebp
  _QWORD *v13; // rax
  unsigned int v14; // ebx
  int v15; // eax
  char *v16; // r9
  unsigned int v17; // r8d
  __int64 v18; // rdx
  unsigned int v19; // ecx
  unsigned int v20; // r8d
  char *i; // r9
  __int64 v22; // rdx
  unsigned int v23; // ecx
  int v25; // [rsp+98h] [rbp+10h]

  v3 = *(_DWORD *)(a2 + 16);
  pbInput = 0;
  v6 = *(_DWORD *)(a2 + 12) + 7;
  v25 = v3;
  v7 = v6 >> 3;
  if ( (v3 & 0xFF000000) != 0 )
  {
    v10 = 4;
  }
  else if ( (v3 & 0xFF0000) != 0 )
  {
    v10 = 3;
  }
  else
  {
    v10 = ((v3 & 0xFF00) != 0) + 1;
  }
  v11 = v7 + 24;
  if ( v7 + 24 < v7 || (cbInput = v11 + v10, v11 + v10 < v11) )
  {
    v14 = -2147024362;
  }
  else
  {
    v13 = CoTaskMemAlloc(cbInput);
    pbInput = v13;
    if ( v13 )
    {
      memset_0(v13, 0, cbInput);
      *(_DWORD *)pbInput = 826364754;
      v15 = *(_DWORD *)(a2 + 12);
      v16 = (char *)(pbInput + 3);
      pbInput[2] = 0;
      v17 = 0;
      *((_DWORD *)pbInput + 1) = v15;
      *((_DWORD *)pbInput + 2) = v10;
      *((_DWORD *)pbInput + 3) = v7;
      do
      {
        v18 = v17;
        v19 = v10 - v17++;
        v16[v19 - 1] = *((_BYTE *)&v25 + v18);
      }
      while ( v17 < v10 );
      v20 = 0;
      for ( i = &v16[v10]; v20 < v7; i[v23 - 1] = *(_BYTE *)(v22 + a2 + 20) )
      {
        v22 = v20;
        v23 = v7 - v20++;
      }
      v14 = BCryptImportKeyPair(hAlgorithm, 0, L"RSAPUBLICBLOB", a3, (PUCHAR)pbInput, cbInput, 0);
    }
    else
    {
      v14 = -2147024882;
    }
  }
  CoTaskMemFree(pbInput);
  return v14;
}

```

## disassembly

```asm
0x180008820  push    rbx
0x180008822  push    rbp
0x180008823  push    rsi
0x180008824  push    rdi
0x180008825  push    r12
0x180008827  push    r13
0x180008829  push    r14
0x18000882b  push    r15
0x18000882d  sub     rsp, 48h
0x180008831  mov     eax, [rdx+10h]
0x180008834  xor     esi, esi
0x180008836  mov     edi, [rdx+0Ch]
0x180008839  mov     r12, r8
0x18000883c  add     edi, 7
0x18000883f  mov     [rsp+88h+arg_8], eax
0x180008846  shr     edi, 3
0x180008849  mov     r15, rdx
0x18000884c  mov     r13, rcx
0x18000884f  test    eax, 0FF000000h
0x180008854  jz      short loc_18000885B
0x180008856  lea     ebx, [rsi+4]
0x180008859  jmp     short loc_180008876
0x18000885b  test    eax, 0FF0000h
0x180008860  jz      short loc_180008869
0x180008862  mov     ebx, 3
0x180008867  jmp     short loc_180008876
0x180008869  and     eax, 0FF00h
0x18000886e  neg     eax
0x180008870  sbb     ebx, ebx
0x180008872  neg     ebx
0x180008874  inc     ebx
0x180008876  lea     eax, [rdi+18h]
0x180008879  cmp     eax, edi
0x18000887b  jb      loc_18000894E
0x180008881  lea     ebp, [rax+rbx]
0x180008884  cmp     ebp, eax
0x180008886  jb      loc_18000894E
0x18000888c  mov     ecx, ebp; cb
0x18000888e  mov     r14d, ebp
0x180008891  call    cs:__imp_CoTaskMemAlloc
0x180008898  nop     dword ptr [rax+rax+00h]
0x18000889d  mov     rsi, rax
0x1800088a0  test    rax, rax
0x1800088a3  jnz     short loc_1800088AF
0x1800088a5  mov     ebx, 8007000Eh
0x1800088aa  jmp     loc_180008953
0x1800088af  mov     r8, r14; Size
0x1800088b2  xor     edx, edx; Val
0x1800088b4  mov     rcx, rsi; void *
0x1800088b7  call    memset_0
0x1800088bc  xor     r10d, r10d
0x1800088bf  mov     dword ptr [rsi], 31415352h
0x1800088c5  mov     eax, [r15+0Ch]
0x1800088c9  lea     r9, [rsi+18h]
0x1800088cd  mov     [rsi+10h], r10
0x1800088d1  mov     r8d, r10d
0x1800088d4  mov     [rsi+4], eax
0x1800088d7  mov     [rsi+8], ebx
0x1800088da  mov     [rsi+0Ch], edi
0x1800088dd  mov     ecx, ebx
0x1800088df  mov     edx, r8d
0x1800088e2  sub     ecx, r8d
0x1800088e5  inc     r8d
0x1800088e8  dec     ecx
0x1800088ea  mov     al, byte ptr [rsp+rdx+88h+arg_8]
0x1800088f1  mov     [rcx+r9], al
0x1800088f5  cmp     r8d, ebx
0x1800088f8  jb      short loc_1800088DD
0x1800088fa  mov     eax, ebx
0x1800088fc  mov     r8d, r10d
0x1800088ff  add     r9, rax
0x180008902  test    edi, edi
0x180008904  jz      short loc_180008921
0x180008906  mov     ecx, edi
0x180008908  mov     edx, r8d
0x18000890b  sub     ecx, r8d
0x18000890e  inc     r8d
0x180008911  dec     ecx
0x180008913  mov     al, [rdx+r15+14h]
0x180008918  mov     [rcx+r9], al
0x18000891c  cmp     r8d, edi
0x18000891f  jb      short loc_180008906
0x180008921  mov     [rsp+88h+dwFlags], r10d; dwFlags
0x180008926  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x18000892d  mov     [rsp+88h+cbInput], ebp; cbInput
0x180008931  mov     r9, r12; phKey
0x180008934  xor     edx, edx; hImportKey
0x180008936  mov     [rsp+88h+pbInput], rsi; pbInput
0x18000893b  mov     rcx, r13; hAlgorithm
0x18000893e  call    cs:__imp_BCryptImportKeyPair
0x180008945  nop     dword ptr [rax+rax+00h]
0x18000894a  mov     ebx, eax
0x18000894c  jmp     short loc_180008953
0x18000894e  mov     ebx, 80070216h
0x180008953  mov     rcx, rsi; pv
0x180008956  call    cs:__imp_CoTaskMemFree
0x18000895d  nop     dword ptr [rax+rax+00h]
0x180008962  mov     eax, ebx
0x180008964  add     rsp, 48h
0x180008968  pop     r15
0x18000896a  pop     r14
0x18000896c  pop     r13
0x18000896e  pop     r12
0x180008970  pop     rdi
0x180008971  pop     rsi
0x180008972  pop     rbp
0x180008973  pop     rbx
0x180008974  retn
```
