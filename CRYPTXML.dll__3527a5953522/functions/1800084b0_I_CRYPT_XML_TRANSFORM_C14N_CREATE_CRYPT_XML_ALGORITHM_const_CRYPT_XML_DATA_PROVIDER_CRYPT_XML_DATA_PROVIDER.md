# I_CRYPT_XML_TRANSFORM_C14N_CREATE(_CRYPT_XML_ALGORITHM const *,_CRYPT_XML_DATA_PROVIDER *,_CRYPT_XML_DATA_PROVIDER *)

- ea: `0x1800084b0`
- end: `0x1800088c3`
- name: `?I_CRYPT_XML_TRANSFORM_C14N_CREATE@@YAJPEBU_CRYPT_XML_ALGORITHM@@PEAU_CRYPT_XML_DATA_PROVIDER@@1@Z`
- size: `1043`
- prototype: `__int64 __fastcall(const struct _CRYPT_XML_ALGORITHM *, struct _CRYPT_XML_DATA_PROVIDER *, struct _CRYPT_XML_DATA_PROVIDER *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800070d0`
- `0x1800084b0`
- `0x180014ce0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800084ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000888e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800084ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000888e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008506`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008506`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088a5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000858f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800085ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008645`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000858f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800085ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008645`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800086ba`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800086ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000865a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000879a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000865a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000879a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087eb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180008785`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180008785`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800087d6`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800087d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008843`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008858`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000886d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008882`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008843`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008858`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000886d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008882`

## string_xrefs

- `0x180008521`: `onecore\ds\security\cryptoapi\xml\lib\c14n.cpp`
- `0x1800085bf`: `onecore\ds\security\cryptoapi\xml\lib\c14n.cpp`
- `0x18000861a`: `onecore\ds\security\cryptoapi\xml\lib\c14n.cpp`
- `0x18000867f`: `onecore\ds\security\cryptoapi\xml\lib\c14n.cpp`
- `0x1800086f4`: `onecore\ds\security\cryptoapi\xml\lib\c14n.cpp`
- `0x1800087b5`: `onecore\ds\security\cryptoapi\xml\lib\c14n.cpp`
- `0x180008806`: `onecore\ds\security\cryptoapi\xml\lib\c14n.cpp`

## pseudocode

```c
__int64 __fastcall I_CRYPT_XML_TRANSFORM_C14N_CREATE(
        const struct _CRYPT_XML_ALGORITHM *a1,
        struct _CRYPT_XML_DATA_PROVIDER *a2,
        struct _CRYPT_XML_DATA_PROVIDER *a3)
{
  ULONG cbBufferSize; // eax
  unsigned int v7; // ecx
  __int64 v8; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v10; // rbx
  const char *v11; // rax
  char v12; // dl
  const char *v13; // r8
  HANDLE EventW; // rax
  signed int v16; // eax
  unsigned int v17; // ebp
  const char *v18; // rax
  unsigned int v19; // r10d
  const char *v20; // r11
  __int64 v21; // r9
  HANDLE v22; // rax
  signed int v23; // eax
  HANDLE v24; // rax
  signed int v25; // eax
  char v26; // dl
  const char *v27; // r8
  HANDLE MutexW; // rax
  signed int v29; // eax
  char v30; // dl
  const char *v31; // r8
  __int128 v32; // xmm1
  HANDLE Thread; // rax
  signed int v34; // eax
  signed int LastError; // eax
  void *v36; // rcx
  void *v37; // rcx
  void *v38; // rcx
  void *v39; // rcx
  HANDLE v40; // rax

  *(_OWORD *)&a3->pvCallbackState = 0;
  *(_OWORD *)&a3->pfnRead = 0;
  cbBufferSize = a2->cbBufferSize;
  a3->cbBufferSize = cbBufferSize;
  if ( cbBufferSize > 0x7FFFFFF8 )
  {
    cbBufferSize = 0x2000;
    a3->cbBufferSize = 0x2000;
LABEL_3:
    v7 = cbBufferSize;
    goto LABEL_4;
  }
  v7 = 512;
  if ( cbBufferSize >= 0x200 )
    goto LABEL_3;
  a3->cbBufferSize = 512;
LABEL_4:
  v8 = v7;
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 8u, v8 + 104);
  if ( v10 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    v10[9] = EventW;
    if ( EventW )
    {
      v22 = CreateEventW(0, 0, 0, 0);
      v10[7] = v22;
      if ( v22 )
      {
        v24 = CreateEventW(0, 0, 0, 0);
        v10[8] = v24;
        if ( v24 )
        {
          MutexW = CreateMutexW(0, 0, 0);
          v10[6] = MutexW;
          if ( MutexW )
          {
            *(_OWORD *)(v10 + 1) = *(_OWORD *)&a2->pvCallbackState;
            v32 = *(_OWORD *)&a2->pfnRead;
            *v10 = a1;
            v17 = 0;
            *(_OWORD *)(v10 + 3) = v32;
            *((_DWORD *)v10 + 20) = a3->cbBufferSize;
            v10[11] = v10 + 13;
            *((_DWORD *)v10 + 21) = 0;
            *((_DWORD *)v10 + 24) = 0;
            a3->pfnRead = (PFN_CRYPT_XML_DATA_PROVIDER_READ)&I_CRYPT_XML_C14N_DATA_PROVIDER_READ;
            a3->pfnClose = (PFN_CRYPT_XML_DATA_PROVIDER_CLOSE)I_CRYPT_XML_TRANSFORM_C14N_PROVIDER_CLOSE;
            a3->pvCallbackState = v10;
            Thread = CreateThread(0, 0, C14N_ROUTINE, v10, 4u, 0);
            v10[5] = Thread;
            if ( Thread )
            {
              if ( ResumeThread(Thread) != -1 )
                return v17;
              LastError = GetLastError();
              v17 = LastError;
              if ( LastError > 0 )
                v17 = (unsigned __int16)LastError | 0x80070000;
              v18 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\c14n.cpp");
              v21 = 673;
            }
            else
            {
              v34 = GetLastError();
              v17 = v34;
              if ( v34 > 0 )
                v17 = (unsigned __int16)v34 | 0x80070000;
              v18 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\c14n.cpp");
              v21 = 666;
            }
          }
          else
          {
            v29 = GetLastError();
            v17 = v29;
            if ( v29 > 0 )
              v17 = (unsigned __int16)v29 | 0x80070000;
            v19 = v17;
            v18 = "";
            do
            {
              v30 = *(v18 - 1);
              v31 = v18--;
            }
            while ( v30 != 92 && v18 > "onecore\\ds\\security\\cryptoapi\\xml\\lib\\c14n.cpp" );
            v20 = "ERROR  : (0x%08x) %s:%u";
            v21 = 635;
            if ( v30 == 92 )
              v18 = v31;
          }
        }
        else
        {
          v25 = GetLastError();
          v17 = v25;
          if ( v25 > 0 )
            v17 = (unsigned __int16)v25 | 0x80070000;
          v19 = v17;
          v18 = "";
          do
          {
            v26 = *(v18 - 1);
            v27 = v18--;
          }
          while ( v26 != 92 && v18 > "onecore\\ds\\security\\cryptoapi\\xml\\lib\\c14n.cpp" );
          v20 = "ERROR  : (0x%08x) %s:%u";
          v21 = 623;
          if ( v26 == 92 )
            v18 = v27;
        }
      }
      else
      {
        v23 = GetLastError();
        v17 = v23;
        if ( v23 > 0 )
          v17 = (unsigned __int16)v23 | 0x80070000;
        v18 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\c14n.cpp");
        v21 = 615;
      }
    }
    else
    {
      v16 = GetLastError();
      v17 = v16;
      if ( v16 > 0 )
        v17 = (unsigned __int16)v16 | 0x80070000;
      v18 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\c14n.cpp");
      v21 = 607;
    }
    WPPTraceLogA(v20, v19, v18, v21);
    *(_OWORD *)&a3->pvCallbackState = 0;
    *(_OWORD *)&a3->pfnRead = 0;
    v36 = (void *)v10[8];
    if ( v36 )
      CloseHandle(v36);
    v37 = (void *)v10[7];
    if ( v37 )
      CloseHandle(v37);
    v38 = (void *)v10[9];
    if ( v38 )
      CloseHandle(v38);
    v39 = (void *)v10[6];
    if ( v39 )
      CloseHandle(v39);
    v40 = GetProcessHeap();
    HeapFree(v40, 8u, v10);
    return v17;
  }
  v11 = "";
  do
  {
    v12 = *(v11 - 1);
    v13 = v11--;
  }
  while ( v12 != 92 && v11 > "onecore\\ds\\security\\cryptoapi\\xml\\lib\\c14n.cpp" );
  if ( v12 == 92 )
    v11 = v13;
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", 2147942414LL, v11, 595);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800084b0  push    rbx
0x1800084b2  push    rbp
0x1800084b3  push    rdi
0x1800084b4  push    r14
0x1800084b6  sub     rsp, 38h
0x1800084ba  xorps   xmm0, xmm0
0x1800084bd  mov     rdi, r8
0x1800084c0  movups  xmmword ptr [r8], xmm0
0x1800084c4  mov     rbp, rdx
0x1800084c7  mov     r14, rcx
0x1800084ca  movups  xmmword ptr [r8+10h], xmm0
0x1800084cf  mov     eax, [rdx+8]
0x1800084d2  mov     [r8+8], eax
0x1800084d6  cmp     eax, 7FFFFFF8h
0x1800084db  jbe     loc_180008567
0x1800084e1  mov     eax, 2000h
0x1800084e6  mov     [r8+8], eax
0x1800084ea  mov     ecx, eax
0x1800084ec  mov     ebx, ecx
0x1800084ee  call    cs:__imp_GetProcessHeap
0x1800084f5  nop     dword ptr [rax+rax+00h]
0x1800084fa  lea     r8, [rbx+68h]; dwBytes
0x1800084fe  mov     edx, 8; dwFlags
0x180008503  mov     rcx, rax; hHeap
0x180008506  call    cs:__imp_HeapAlloc
0x18000850d  nop     dword ptr [rax+rax+00h]
0x180008512  mov     rbx, rax
0x180008515  test    rax, rax
0x180008518  jnz     short loc_18000857D
0x18000851a  lea     rax, aOnecoreDsSecur_13+2Eh; ""
0x180008521  lea     rcx, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180008528  movzx   edx, byte ptr [rax-1]
0x18000852c  mov     r8, rax
0x18000852f  dec     rax
0x180008532  cmp     dl, 5Ch ; '\'
0x180008535  jz      short loc_18000853C
0x180008537  cmp     rax, rcx
0x18000853a  ja      short loc_180008528
0x18000853c  cmp     dl, 5Ch ; '\'
0x18000853f  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180008546  mov     r9d, 253h
0x18000854c  mov     edx, 8007000Eh
0x180008551  cmovz   rax, r8
0x180008555  mov     r8, rax
0x180008558  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000855d  mov     eax, 8007000Eh
0x180008562  jmp     loc_1800088B8
0x180008567  mov     ecx, 200h
0x18000856c  cmp     eax, ecx
0x18000856e  jnb     loc_1800084EA
0x180008574  mov     [r8+8], ecx
0x180008578  jmp     loc_1800084EC
0x18000857d  xor     r9d, r9d; lpName
0x180008580  mov     [rsp+58h+arg_0], rsi
0x180008585  xor     r8d, r8d; bInitialState
0x180008588  mov     edx, 1; bManualReset
0x18000858d  xor     ecx, ecx; lpEventAttributes
0x18000858f  call    cs:__imp_CreateEventW
0x180008596  nop     dword ptr [rax+rax+00h]
0x18000859b  mov     [rbx+48h], rax
0x18000859f  test    rax, rax
0x1800085a2  jnz     short loc_1800085E0
0x1800085a4  call    cs:__imp_GetLastError
0x1800085ab  nop     dword ptr [rax+rax+00h]
0x1800085b0  mov     ebp, eax
0x1800085b2  test    eax, eax
0x1800085b4  jle     short loc_1800085BF
0x1800085b6  movzx   ebp, ax
0x1800085b9  or      ebp, 80070000h
0x1800085bf  lea     rcx, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800085c6  mov     r10d, ebp
0x1800085c9  lea     r11, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800085d0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800085d5  mov     r9d, 25Fh
0x1800085db  jmp     loc_180008822
0x1800085e0  xor     r9d, r9d; lpName
0x1800085e3  xor     r8d, r8d; bInitialState
0x1800085e6  xor     edx, edx; bManualReset
0x1800085e8  xor     ecx, ecx; lpEventAttributes
0x1800085ea  call    cs:__imp_CreateEventW
0x1800085f1  nop     dword ptr [rax+rax+00h]
0x1800085f6  mov     [rbx+38h], rax
0x1800085fa  test    rax, rax
0x1800085fd  jnz     short loc_18000863B
0x1800085ff  call    cs:__imp_GetLastError
0x180008606  nop     dword ptr [rax+rax+00h]
0x18000860b  mov     ebp, eax
0x18000860d  test    eax, eax
0x18000860f  jle     short loc_18000861A
0x180008611  movzx   ebp, ax
0x180008614  or      ebp, 80070000h
0x18000861a  lea     rcx, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180008621  mov     r10d, ebp
0x180008624  lea     r11, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000862b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180008630  mov     r9d, 267h
0x180008636  jmp     loc_180008822
0x18000863b  xor     r9d, r9d; lpName
0x18000863e  xor     r8d, r8d; bInitialState
0x180008641  xor     edx, edx; bManualReset
0x180008643  xor     ecx, ecx; lpEventAttributes
0x180008645  call    cs:__imp_CreateEventW
0x18000864c  nop     dword ptr [rax+rax+00h]
0x180008651  mov     [rbx+40h], rax
0x180008655  test    rax, rax
0x180008658  jnz     short loc_1800086B3
0x18000865a  call    cs:__imp_GetLastError
0x180008661  nop     dword ptr [rax+rax+00h]
0x180008666  mov     ebp, eax
0x180008668  test    eax, eax
0x18000866a  jle     short loc_180008675
0x18000866c  movzx   ebp, ax
0x18000866f  or      ebp, 80070000h
0x180008675  mov     r10d, ebp
0x180008678  lea     rax, aOnecoreDsSecur_13+2Eh; ""
0x18000867f  lea     rcx, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180008686  movzx   edx, byte ptr [rax-1]
0x18000868a  mov     r8, rax
0x18000868d  dec     rax
0x180008690  cmp     dl, 5Ch ; '\'
0x180008693  jz      short loc_18000869A
0x180008695  cmp     rax, rcx
0x180008698  ja      short loc_180008686
0x18000869a  cmp     dl, 5Ch ; '\'
0x18000869d  lea     r11, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800086a4  mov     r9d, 26Fh
0x1800086aa  cmovz   rax, r8
0x1800086ae  jmp     loc_180008822
0x1800086b3  xor     r8d, r8d; lpName
0x1800086b6  xor     edx, edx; bInitialOwner
0x1800086b8  xor     ecx, ecx; lpMutexAttributes
0x1800086ba  call    cs:__imp_CreateMutexW
0x1800086c1  nop     dword ptr [rax+rax+00h]
0x1800086c6  mov     [rbx+30h], rax
0x1800086ca  test    rax, rax
0x1800086cd  jnz     short loc_180008728
0x1800086cf  call    cs:__imp_GetLastError
0x1800086d6  nop     dword ptr [rax+rax+00h]
0x1800086db  mov     ebp, eax
0x1800086dd  test    eax, eax
0x1800086df  jle     short loc_1800086EA
0x1800086e1  movzx   ebp, ax
0x1800086e4  or      ebp, 80070000h
0x1800086ea  mov     r10d, ebp
0x1800086ed  lea     rax, aOnecoreDsSecur_13+2Eh; ""
0x1800086f4  lea     rcx, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800086fb  movzx   edx, byte ptr [rax-1]
0x1800086ff  mov     r8, rax
0x180008702  dec     rax
0x180008705  cmp     dl, 5Ch ; '\'
0x180008708  jz      short loc_18000870F
0x18000870a  cmp     rax, rcx
0x18000870d  ja      short loc_1800086FB
0x18000870f  cmp     dl, 5Ch ; '\'
0x180008712  lea     r11, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180008719  mov     r9d, 27Bh
0x18000871f  cmovz   rax, r8
0x180008723  jmp     loc_180008822
0x180008728  movups  xmm0, xmmword ptr [rbp+0]
0x18000872c  mov     r9, rbx; lpParameter
0x18000872f  lea     r8, C14N_ROUTINE; lpStartAddress
0x180008736  xor     edx, edx; dwStackSize
0x180008738  xor     ecx, ecx; lpThreadAttributes
0x18000873a  movups  xmmword ptr [rbx+8], xmm0
0x18000873e  movups  xmm1, xmmword ptr [rbp+10h]
0x180008742  mov     [rbx], r14
0x180008745  xor     ebp, ebp
0x180008747  mov     [rsp+58h+lpThreadId], rbp; lpThreadId
0x18000874c  movups  xmmword ptr [rbx+18h], xmm1
0x180008750  mov     eax, [rdi+8]
0x180008753  mov     [rbx+50h], eax
0x180008756  lea     rax, [rbx+68h]
0x18000875a  mov     [rbx+58h], rax
0x18000875e  lea     rax, I_CRYPT_XML_C14N_DATA_PROVIDER_READ
0x180008765  mov     [rbx+54h], ebp
0x180008768  mov     [rbx+60h], ebp
0x18000876b  mov     [rdi+10h], rax
0x18000876f  lea     rax, I_CRYPT_XML_TRANSFORM_C14N_PROVIDER_CLOSE
0x180008776  mov     [rdi+18h], rax
0x18000877a  mov     [rdi], rbx
0x18000877d  mov     [rsp+58h+dwCreationFlags], 4; dwCreationFlags
0x180008785  call    cs:__imp_CreateThread
0x18000878c  nop     dword ptr [rax+rax+00h]
0x180008791  mov     [rbx+28h], rax
0x180008795  test    rax, rax
0x180008798  jnz     short loc_1800087D3
0x18000879a  call    cs:__imp_GetLastError
0x1800087a1  nop     dword ptr [rax+rax+00h]
0x1800087a6  mov     ebp, eax
0x1800087a8  test    eax, eax
0x1800087aa  jle     short loc_1800087B5
0x1800087ac  movzx   ebp, ax
0x1800087af  or      ebp, 80070000h
0x1800087b5  lea     rcx, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800087bc  mov     r10d, ebp
0x1800087bf  lea     r11, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800087c6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800087cb  mov     r9d, 29Ah
0x1800087d1  jmp     short loc_180008822
0x1800087d3  mov     rcx, rax; hThread
0x1800087d6  call    cs:__imp_ResumeThread
0x1800087dd  nop     dword ptr [rax+rax+00h]
0x1800087e2  cmp     eax, 0FFFFFFFFh
0x1800087e5  jnz     loc_1800088B1
0x1800087eb  call    cs:__imp_GetLastError
0x1800087f2  nop     dword ptr [rax+rax+00h]
0x1800087f7  mov     ebp, eax
0x1800087f9  test    eax, eax
0x1800087fb  jle     short loc_180008806
0x1800087fd  movzx   ebp, ax
0x180008800  or      ebp, 80070000h
0x180008806  lea     rcx, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000880d  mov     r10d, ebp
0x180008810  lea     r11, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180008817  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000881c  mov     r9d, 2A1h
0x180008822  mov     r8, rax
0x180008825  mov     edx, r10d
0x180008828  mov     rcx, r11; char *
0x18000882b  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180008830  xorps   xmm0, xmm0
0x180008833  movups  xmmword ptr [rdi], xmm0
0x180008836  movups  xmmword ptr [rdi+10h], xmm0
0x18000883a  mov     rcx, [rbx+40h]; hObject
0x18000883e  test    rcx, rcx
0x180008841  jz      short loc_18000884F
0x180008843  call    cs:__imp_CloseHandle
0x18000884a  nop     dword ptr [rax+rax+00h]
0x18000884f  mov     rcx, [rbx+38h]; hObject
0x180008853  test    rcx, rcx
0x180008856  jz      short loc_180008864
0x180008858  call    cs:__imp_CloseHandle
0x18000885f  nop     dword ptr [rax+rax+00h]
0x180008864  mov     rcx, [rbx+48h]; hObject
0x180008868  test    rcx, rcx
0x18000886b  jz      short loc_180008879
0x18000886d  call    cs:__imp_CloseHandle
0x180008874  nop     dword ptr [rax+rax+00h]
0x180008879  mov     rcx, [rbx+30h]; hObject
0x18000887d  test    rcx, rcx
0x180008880  jz      short loc_18000888E
0x180008882  call    cs:__imp_CloseHandle
0x180008889  nop     dword ptr [rax+rax+00h]
0x18000888e  call    cs:__imp_GetProcessHeap
0x180008895  nop     dword ptr [rax+rax+00h]
0x18000889a  mov     r8, rbx; lpMem
0x18000889d  mov     edx, 8; dwFlags
0x1800088a2  mov     rcx, rax; hHeap
0x1800088a5  call    cs:__imp_HeapFree
0x1800088ac  nop     dword ptr [rax+rax+00h]
0x1800088b1  mov     rsi, [rsp+58h+arg_0]
0x1800088b6  mov     eax, ebp
0x1800088b8  add     rsp, 38h
0x1800088bc  pop     r14
0x1800088be  pop     rdi
0x1800088bf  pop     rbp
0x1800088c0  pop     rbx
0x1800088c1  retn
```
