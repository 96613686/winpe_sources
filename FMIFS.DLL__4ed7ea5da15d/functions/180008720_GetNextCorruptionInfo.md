# GetNextCorruptionInfo

- ea: `0x180008720`
- end: `0x180008a81`
- name: `GetNextCorruptionInfo`
- size: `865`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800070d0`

## callees

- `0x180008720`
- `0x180009746`
- `0x180009752`
- `0x18000a010`

## import_xrefs

- `msvcrt!malloc` at `0x180008761`
- `msvcrt!malloc` at `0x180008761`
- `msvcrt!free` at `0x180008a45`
- `msvcrt!free` at `0x180008a53`
- `msvcrt!free` at `0x180008a45`
- `msvcrt!free` at `0x180008a53`
- `msvcrt!realloc` at `0x1800087af`
- `msvcrt!realloc` at `0x180008840`
- `msvcrt!realloc` at `0x1800088a6`
- `msvcrt!realloc` at `0x1800089dc`
- `msvcrt!realloc` at `0x1800087af`
- `msvcrt!realloc` at `0x180008840`
- `msvcrt!realloc` at `0x1800088a6`
- `msvcrt!realloc` at `0x1800089dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000881c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000881c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008a3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008a60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008a3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008a60`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800087fe`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800087fe`

## pseudocode

```c
char __fastcall GetNextCorruptionInfo(__int64 a1, int a2, void **a3)
{
  char v5; // bp
  char *v6; // rax
  void *v7; // r14
  DWORD v8; // ecx
  DWORD *v9; // r13
  DWORD nOutBufferSize; // r15d
  DWORD *v11; // rax
  DWORD *lpOutBuffer; // rbx
  _OWORD *v13; // rax
  char v14; // r8
  DWORD *v15; // rbx
  unsigned int v16; // r12d
  char *v17; // rax
  signed int v18; // ecx
  _DWORD *v19; // rdx
  char *v20; // rdi
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  char *v35; // rax
  int v37; // [rsp+90h] [rbp+8h] BYREF
  int v38; // [rsp+98h] [rbp+10h]

  v38 = a2;
  v37 = 0;
  v5 = 0;
  if ( (unsigned __int64)(a1 - 1) > 0xFFFFFFFFFFFFFFFDuLL || !a3 )
  {
    v8 = 87;
    goto LABEL_52;
  }
  v6 = (char *)malloc(0x24u);
  v7 = v6;
  if ( !v6 )
  {
    v8 = 8;
LABEL_52:
    SetLastError(v8);
    return v5;
  }
  *((_DWORD *)v6 + 5) = 0;
  v9 = 0;
  *((_DWORD *)v6 + 8) = 0;
  nOutBufferSize = 1024;
  *(_DWORD *)v6 = 2;
  *((_DWORD *)v6 + 1) = 35;
  *((_DWORD *)v6 + 2) = 1;
  *(_QWORD *)(v6 + 12) = 0;
  *((_QWORD *)v6 + 3) = *(_QWORD *)(a1 + 8);
  while ( 1 )
  {
    v11 = (DWORD *)realloc(v9, nOutBufferSize);
    lpOutBuffer = v11;
    if ( !v11 )
      goto LABEL_47;
    v9 = v11;
    memset_0(v11, 0, nOutBufferSize);
    if ( DeviceIoControl(*(HANDLE *)a1, 0x90260u, v7, 0x24u, lpOutBuffer, nOutBufferSize, 0, 0) )
      break;
    if ( GetLastError() == 234 )
      nOutBufferSize = *lpOutBuffer;
    if ( GetLastError() != 234 )
      goto LABEL_49;
  }
  *(_QWORD *)(a1 + 8) = *(_QWORD *)(lpOutBuffer + 3);
  v13 = realloc(*a3, 0x20u);
  if ( v13 )
  {
    v14 = v38;
    *a3 = v13;
    *v13 = 0;
    v15 = lpOutBuffer + 6;
    v16 = 0;
    v13[1] = 0;
    *(_BYTE *)*a3 = 1;
    *((_BYTE *)*a3 + 1) = 0;
    *((_DWORD *)*a3 + 1) = *((unsigned __int16 *)v15 + 12);
    if ( (v14 & 1) == 0 )
      goto LABEL_17;
    v17 = (char *)realloc(*a3, 0x1020u);
    if ( v17 )
    {
      *a3 = v17;
      *((_QWORD *)v17 + 1) = v17 + 32;
      v18 = (*(__int64 (__fastcall **)(_QWORD, DWORD *, __int64, _QWORD, int, _DWORD, int, int, int *))(a1 + 48))(
              0,
              v15,
              (__int64)v7 + 24,
              *((_QWORD *)*a3 + 1),
              2048,
              0,
              4,
              75,
              &v37);
      v16 = 2 * v37;
      if ( v18 < 0 )
        goto LABEL_48;
      v14 = v38;
LABEL_17:
      v19 = *a3;
      v20 = 0;
      v21 = *((_DWORD *)*a3 + 1);
      if ( v21 > 9 )
      {
        v28 = v21 - 10;
        if ( v28 )
        {
          v29 = v28 - 1;
          if ( v29 )
          {
            v30 = v29 - 1;
            if ( v30 )
            {
              v31 = v30 - 1;
              if ( v31 )
              {
                v32 = v31 - 1;
                if ( v32 )
                {
                  v33 = v32 - 1;
                  if ( !v33 )
                  {
                    v19[4] = *(DWORD *)((char *)v15 + 2 * *((unsigned __int8 *)v15 + 45) + 54);
                    v20 = (char *)v15 + 2 * *((unsigned __int8 *)v15 + 45) + 58;
                    goto LABEL_40;
                  }
                  v34 = v33 - 1;
                  if ( !v34 )
                  {
                    v19[4] = 2;
                    goto LABEL_39;
                  }
                  if ( v34 != 1 )
                    goto LABEL_40;
                }
              }
            }
          }
        }
      }
      else
      {
        if ( v21 == 9 )
        {
          v20 = (char *)(v15 + 10);
          v19[4] = v15[9];
          goto LABEL_40;
        }
        if ( !v21 || (v22 = v21 - 1) == 0 || (v23 = v22 - 1) == 0 )
        {
LABEL_27:
          v19[4] = 0;
          goto LABEL_40;
        }
        v24 = v23 - 1;
        if ( v24 )
        {
          v25 = v24 - 1;
          if ( v25 )
          {
            v26 = v25 - 1;
            if ( v26 )
            {
              v27 = v26 - 1;
              if ( v27 )
              {
                if ( v27 - 1 > 1 )
                  goto LABEL_40;
              }
            }
            goto LABEL_27;
          }
          v20 = (char *)(v15 + 9);
          v19[4] = v15[8];
LABEL_40:
          if ( (v14 & 2) == 0 || !v20 )
            goto LABEL_44;
          v35 = (char *)realloc(*a3, 2 * (v16 + 4 * (*((unsigned int *)*a3 + 4) + 4LL)));
          if ( v35 )
          {
            *a3 = v35;
            *((_QWORD *)v35 + 3) = &v35[2 * v16 + 32];
            memcpy_0(*((void **)*a3 + 3), v20, 8LL * *((unsigned int *)*a3 + 4));
LABEL_44:
            v5 = 1;
            goto LABEL_49;
          }
          goto LABEL_47;
        }
      }
      v19[4] = 1;
LABEL_39:
      v20 = (char *)(v15 + 8);
      goto LABEL_40;
    }
  }
LABEL_47:
  v18 = 8;
LABEL_48:
  SetLastError(v18);
LABEL_49:
  free(v7);
  if ( v9 )
    free(v9);
  return v5;
}

```

## disassembly

```asm
0x180008720  mov     rax, rsp
0x180008723  mov     [rax+18h], rbx
0x180008727  mov     [rax+10h], edx
0x18000872a  push    rbp
0x18000872b  push    rsi
0x18000872c  push    rdi
0x18000872d  push    r12
0x18000872f  push    r13
0x180008731  push    r14
0x180008733  push    r15
0x180008735  sub     rsp, 50h
0x180008739  xor     ebx, ebx
0x18000873b  mov     rsi, r8
0x18000873e  mov     [rax+8], ebx
0x180008741  mov     rdi, rcx
0x180008744  lea     rax, [rcx-1]
0x180008748  mov     bpl, bl
0x18000874b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000874f  ja      loc_180008A5B
0x180008755  test    r8, r8
0x180008758  jz      loc_180008A5B
0x18000875e  lea     ecx, [rbx+24h]; Size
0x180008761  call    cs:__imp_malloc
0x180008767  mov     r14, rax
0x18000876a  test    rax, rax
0x18000876d  jnz     short loc_180008777
0x18000876f  lea     ecx, [rbx+8]
0x180008772  jmp     loc_180008A60
0x180008777  mov     [rax+14h], ebx
0x18000877a  mov     r13, rbx
0x18000877d  mov     [rax+20h], ebx
0x180008780  mov     r15d, 400h
0x180008786  mov     dword ptr [rax], 2
0x18000878c  mov     dword ptr [rax+4], 23h ; '#'
0x180008793  mov     dword ptr [rax+8], 1
0x18000879a  mov     [rax+0Ch], rbx
0x18000879e  mov     rax, [rdi+8]
0x1800087a2  mov     [r14+18h], rax
0x1800087a6  mov     edx, r15d; Size
0x1800087a9  mov     rcx, r13; Block
0x1800087ac  mov     r12d, r15d
0x1800087af  call    cs:__imp_realloc
0x1800087b5  mov     rbx, rax
0x1800087b8  test    rax, rax
0x1800087bb  jz      loc_180008A37
0x1800087c1  mov     r8d, r12d; Size
0x1800087c4  xor     edx, edx; Val
0x1800087c6  mov     rcx, rax; void *
0x1800087c9  mov     r13, rax
0x1800087cc  call    memset_0
0x1800087d1  mov     rcx, [rdi]; hDevice
0x1800087d4  mov     r9d, 24h ; '$'; nInBufferSize
0x1800087da  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x1800087e3  mov     r8, r14; lpInBuffer
0x1800087e6  mov     [rsp+88h+lpBytesReturned], 0; lpBytesReturned
0x1800087ef  mov     edx, 90260h; dwIoControlCode
0x1800087f4  mov     [rsp+88h+nOutBufferSize], r15d; nOutBufferSize
0x1800087f9  mov     [rsp+88h+lpOutBuffer], rbx; lpOutBuffer
0x1800087fe  call    cs:__imp_DeviceIoControl
0x180008804  test    eax, eax
0x180008806  jnz     short loc_180008830
0x180008808  call    cs:__imp_GetLastError
0x18000880e  mov     r12d, 0EAh
0x180008814  cmp     eax, r12d
0x180008817  jnz     short loc_18000881C
0x180008819  mov     r15d, [rbx]
0x18000881c  call    cs:__imp_GetLastError
0x180008822  cmp     eax, r12d
0x180008825  jz      loc_1800087A6
0x18000882b  jmp     loc_180008A42
0x180008830  mov     rax, [rbx+0Ch]
0x180008834  mov     edx, 20h ; ' '; Size
0x180008839  mov     [rdi+8], rax
0x18000883d  mov     rcx, [rsi]; Block
0x180008840  call    cs:__imp_realloc
0x180008846  xor     r9d, r9d
0x180008849  test    rax, rax
0x18000884c  jz      loc_180008A37
0x180008852  mov     r8d, [rsp+88h+arg_8]
0x18000885a  lea     r15d, [r9+1]
0x18000885e  mov     [rsi], rax
0x180008861  xorps   xmm0, xmm0
0x180008864  movups  xmmword ptr [rax], xmm0
0x180008867  add     rbx, 18h
0x18000886b  mov     r12d, r9d
0x18000886e  movups  xmmword ptr [rax+10h], xmm0
0x180008872  mov     rax, [rsi]
0x180008875  mov     [rax], r15b
0x180008878  mov     rax, [rsi]
0x18000887b  mov     [rax+1], r9b
0x18000887f  mov     rax, [rsi]
0x180008882  movzx   ecx, word ptr [rbx+18h]
0x180008886  mov     [rax+4], ecx
0x180008889  test    r15b, r8b
0x18000888c  jz      loc_180008933
0x180008892  mov     r12d, 800h
0x180008898  mov     rcx, [rsi]; Block
0x18000889b  mov     edx, r12d
0x18000889e  lea     rdx, ds:20h[rdx*2]; Size
0x1800088a6  call    cs:__imp_realloc
0x1800088ac  mov     rcx, rax
0x1800088af  test    rax, rax
0x1800088b2  jz      loc_180008A37
0x1800088b8  mov     [rsi], rax
0x1800088bb  lea     r8, [r14+18h]
0x1800088bf  add     rax, 20h ; ' '
0x1800088c3  mov     rdx, rbx
0x1800088c6  mov     [rcx+8], rax
0x1800088ca  lea     rax, [rsp+88h+arg_0]
0x1800088d2  mov     r9, [rsi]
0x1800088d5  xor     ecx, ecx
0x1800088d7  mov     [rsp+88h+var_48], rax
0x1800088dc  mov     rax, [rdi+30h]
0x1800088e0  mov     dword ptr [rsp+88h+lpOverlapped], 4Bh ; 'K'
0x1800088e8  mov     r9, [r9+8]
0x1800088ec  mov     dword ptr [rsp+88h+lpBytesReturned], 4
0x1800088f4  mov     [rsp+88h+nOutBufferSize], 0
0x1800088fc  mov     dword ptr [rsp+88h+lpOutBuffer], r12d
0x180008901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008906  mov     ecx, eax
0x180008908  xor     r9d, r9d
0x18000890b  mov     eax, [rsp+88h+arg_0]
0x180008912  lea     r12d, [rax+rax]
0x180008916  test    ecx, ecx
0x180008918  jns     short loc_18000892B
0x18000891a  cmp     ecx, 0EAh
0x180008920  jz      loc_180008898
0x180008926  jmp     loc_180008A3C
0x18000892b  mov     r8d, [rsp+88h+arg_8]
0x180008933  mov     rdx, [rsi]
0x180008936  mov     rdi, r9
0x180008939  mov     eax, [rdx+4]
0x18000893c  cmp     eax, 9
0x18000893f  ja      short loc_18000898D
0x180008941  jz      short loc_180008981
0x180008943  test    eax, eax
0x180008945  jz      short loc_18000896F
0x180008947  sub     eax, 1
0x18000894a  jz      short loc_18000896F
0x18000894c  sub     eax, 1
0x18000894f  jz      short loc_18000896F
0x180008951  sub     eax, 1
0x180008954  jz      short loc_1800089B5
0x180008956  sub     eax, 1
0x180008959  jz      short loc_180008975
0x18000895b  sub     eax, 1
0x18000895e  jz      short loc_18000896F
0x180008960  sub     eax, 1
0x180008963  jz      short loc_18000896F
0x180008965  sub     eax, 1
0x180008968  jz      short loc_18000896F
0x18000896a  cmp     eax, 1
0x18000896d  jnz     short loc_1800089BD
0x18000896f  mov     [rdx+10h], r9d
0x180008973  jmp     short loc_1800089BD
0x180008975  mov     eax, [rbx+20h]
0x180008978  lea     rdi, [rbx+24h]
0x18000897c  mov     [rdx+10h], eax
0x18000897f  jmp     short loc_1800089BD
0x180008981  mov     eax, [rbx+24h]
0x180008984  lea     rdi, [rbx+28h]
0x180008988  mov     [rdx+10h], eax
0x18000898b  jmp     short loc_1800089BD
0x18000898d  sub     eax, 0Ah
0x180008990  jz      short loc_1800089B5
0x180008992  sub     eax, 1
0x180008995  jz      short loc_1800089B5
0x180008997  sub     eax, 1
0x18000899a  jz      short loc_1800089B5
0x18000899c  sub     eax, 1
0x18000899f  jz      short loc_1800089B5
0x1800089a1  sub     eax, 1
0x1800089a4  jz      short loc_1800089B5
0x1800089a6  sub     eax, 1
0x1800089a9  jz      short loc_180008A1E
0x1800089ab  sub     eax, 1
0x1800089ae  jz      short loc_180008A15
0x1800089b0  cmp     eax, 1
0x1800089b3  jnz     short loc_1800089BD
0x1800089b5  mov     [rdx+10h], r15d
0x1800089b9  lea     rdi, [rbx+20h]
0x1800089bd  test    r8b, 2
0x1800089c1  jz      short loc_180008A10
0x1800089c3  test    rdi, rdi
0x1800089c6  jz      short loc_180008A10
0x1800089c8  mov     rcx, [rsi]; Block
0x1800089cb  mov     ebx, r12d
0x1800089ce  mov     eax, [rcx+10h]
0x1800089d1  add     rax, 4
0x1800089d5  lea     rdx, [rbx+rax*4]
0x1800089d9  add     rdx, rdx; Size
0x1800089dc  call    cs:__imp_realloc
0x1800089e2  mov     rcx, rax
0x1800089e5  test    rax, rax
0x1800089e8  jz      short loc_180008A37
0x1800089ea  mov     [rsi], rax
0x1800089ed  mov     rdx, rdi; Src
0x1800089f0  lea     rax, [rbx+10h]
0x1800089f4  lea     rax, [rcx+rax*2]
0x1800089f8  mov     [rcx+18h], rax
0x1800089fc  mov     rcx, [rsi]
0x1800089ff  mov     r8d, [rcx+10h]
0x180008a03  mov     rcx, [rcx+18h]; void *
0x180008a07  shl     r8, 3; Size
0x180008a0b  call    memcpy_0
0x180008a10  mov     bpl, r15b
0x180008a13  jmp     short loc_180008A42
0x180008a15  mov     dword ptr [rdx+10h], 2
0x180008a1c  jmp     short loc_1800089B9
0x180008a1e  movzx   eax, byte ptr [rbx+2Dh]
0x180008a22  mov     ecx, [rbx+rax*2+36h]
0x180008a26  mov     [rdx+10h], ecx
0x180008a29  movzx   edi, byte ptr [rbx+2Dh]
0x180008a2d  add     rdi, 1Dh
0x180008a31  lea     rdi, [rbx+rdi*2]
0x180008a35  jmp     short loc_1800089BD
0x180008a37  mov     ecx, 8; dwErrCode
0x180008a3c  call    cs:__imp_SetLastError
0x180008a42  mov     rcx, r14; Block
0x180008a45  call    cs:__imp_free
0x180008a4b  test    r13, r13
0x180008a4e  jz      short loc_180008A66
0x180008a50  mov     rcx, r13; Block
0x180008a53  call    cs:__imp_free
0x180008a59  jmp     short loc_180008A66
0x180008a5b  mov     ecx, 57h ; 'W'; dwErrCode
0x180008a60  call    cs:__imp_SetLastError
0x180008a66  mov     rbx, [rsp+88h+arg_10]
0x180008a6e  mov     al, bpl
0x180008a71  add     rsp, 50h
0x180008a75  pop     r15
0x180008a77  pop     r14
0x180008a79  pop     r13
0x180008a7b  pop     r12
0x180008a7d  pop     rdi
0x180008a7e  pop     rsi
0x180008a7f  pop     rbp
0x180008a80  retn
```
