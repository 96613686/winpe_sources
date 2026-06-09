# Windows::UI::Input::Preview::Injection::InputInjector::InjectTouchInput(Windows::Foundation::Collections::IIterable<Windows::UI::Input::Preview::Injection::InjectedInputTouchInfo *> *)

- ea: `0x18000c440`
- end: `0x18000c8b3`
- name: `?InjectTouchInput@InputInjector@Injection@Preview@Input@UI@Windows@@UEAAJPEAU?$IIterable@PEAVInjectedInputTouchInfo@Injection@Preview@Input@UI@Windows@@@Collections@Foundation@6@@Z`
- size: `1139`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000c440`
- `0x180011460`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c864`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c864`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c783`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c783`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c81d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c81d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c856`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c856`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c4a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c4a3`
- `ext-ms-win-ntuser-rim-l1-1-0!InjectPointerInput` at `0x18000c813`
- `ext-ms-win-ntuser-rim-l1-1-0!InjectPointerInput` at `0x18000c813`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Preview::Injection::InputInjector::InjectTouchInput(__int64 a1, __int64 a2)
{
  int v4; // r12d
  char *v5; // rsi
  signed int v6; // ebx
  __int64 v7; // rbx
  char *v8; // rax
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // r14
  int v14; // eax
  int v15; // ecx
  int v16; // edx
  int v17; // r8d
  int v18; // eax
  int v19; // edx
  int v20; // r9d
  int v21; // r8d
  int v22; // ecx
  int v23; // r10d
  __int64 v24; // rax
  double v25; // xmm1_8
  signed int LastError; // eax
  __int64 v27; // rcx
  _BYTE v29[8]; // [rsp+28h] [rbp-59h] BYREF
  __int64 v30; // [rsp+30h] [rbp-51h] BYREF
  __int64 v31; // [rsp+38h] [rbp-49h] BYREF
  __int128 v32; // [rsp+40h] [rbp-41h]
  __int128 v33; // [rsp+50h] [rbp-31h]
  _OWORD v34[2]; // [rsp+60h] [rbp-21h] BYREF
  __int128 v35; // [rsp+80h] [rbp-1h] BYREF
  __int128 v36; // [rsp+90h] [rbp+Fh]

  v4 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  memset(v34, 0, 28);
  if ( a2 )
  {
    v7 = 38760;
    v8 = (char *)CoTaskMemAlloc(0x9768u);
    v5 = v8;
    if ( v8 )
    {
      do
      {
        *v8++ = 0;
        --v7;
      }
      while ( v7 );
      v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 48LL);
      v10 = v31;
      if ( v31 )
      {
        v31 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      v6 = v9(a2, &v31);
      if ( v6 >= 0 )
      {
        v29[0] = 0;
        v6 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v31 + 56LL))(v31, v29);
        while ( v6 >= 0 )
        {
          if ( !v29[0] )
            break;
          if ( v4 < 255 )
          {
            v30 = 0;
            v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 48LL))(v31, &v30);
            v6 = v12;
            v11 = v30;
            if ( v30 )
            {
              if ( v12 >= 0 )
              {
                v13 = 152LL * v4;
                *(_DWORD *)&v5[v13] = 2;
                *(_DWORD *)&v5[v13 + 8] = 2;
                v35 = 0;
                v6 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v11 + 48LL))(v11, &v35);
                if ( v6 >= 0 )
                {
                  v14 = DWORD1(v35);
                  *(_DWORD *)&v5[v13 + 116] = DWORD1(v35);
                  v15 = v35;
                  *(_DWORD *)&v5[v13 + 112] = v35;
                  v16 = DWORD2(v35);
                  *(_DWORD *)&v5[v13 + 124] = DWORD2(v35);
                  v17 = HIDWORD(v35);
                  *(_DWORD *)&v5[v13 + 120] = HIDWORD(v35);
                  if ( v14 || v15 || v16 || v17 )
                    ++HIDWORD(v33);
                  LODWORD(v35) = 0;
                  v6 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v30 + 64LL))(v30, &v35);
                  if ( v6 >= 0 )
                  {
                    v18 = v35;
                    *(_DWORD *)&v5[v13 + 144] = v35;
                    if ( v18 )
                      ++LODWORD(v34[0]);
                    v35 = 0;
                    v36 = 0;
                    v6 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v30 + 80LL))(v30, &v35);
                    if ( v6 >= 0 )
                    {
                      v19 = v35;
                      v20 = DWORD1(v35);
                      v21 = DWORD2(v35);
                      v22 = HIDWORD(v35);
                      v23 = v36;
                      v24 = *((_QWORD *)&v36 + 1);
                      *(_QWORD *)&v5[v13 + 88] = *((_QWORD *)&v36 + 1);
                      if ( v24 )
                        ++DWORD1(v34[1]);
                      *(_DWORD *)&v5[v13 + 40] = v21;
                      *(_DWORD *)&v5[v13 + 44] = v22;
                      if ( (v21 | v22) > 0 )
                        ++HIDWORD(v34[0]);
                      *(_DWORD *)&v5[v13 + 12] = v19;
                      if ( v19 )
                        ++DWORD2(v34[0]);
                      *(_DWORD *)&v5[v13 + 20] = v20;
                      DWORD2(v34[1]) |= v20;
                      *(_DWORD *)&v5[v13 + 72] = v23;
                      if ( v23 )
                        ++LODWORD(v34[1]);
                      *(_QWORD *)&v35 = 0;
                      v6 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v30 + 96LL))(v30, &v35);
                      if ( v6 >= 0 )
                      {
                        v25 = *(double *)&v35;
                        if ( *(double *)&v35 > 1.0 || *(double *)&v35 < 0.0 )
                        {
                          v6 = -2147024809;
                        }
                        else
                        {
                          v6 = 0;
                          *(_DWORD *)&v5[v13 + 148] = (int)(*(double *)&v35 * 1024.0);
                        }
                        if ( v25 != 0.0 )
                          ++DWORD1(v34[0]);
                        if ( v6 >= 0 )
                        {
                          LODWORD(v35) = 0;
                          v6 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v30 + 112LL))(v30, &v35);
                          if ( v6 >= 0 )
                          {
                            *(_DWORD *)&v5[v13 + 108] = v35;
                            v6 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v31 + 64LL))(v31, v29);
                            ++v4;
                          }
                        }
                      }
                    }
                  }
                }
                v11 = v30;
              }
            }
            else
            {
              v6 = -2147024809;
            }
          }
          else
          {
            v6 = -2147024809;
            ++DWORD2(v32);
            v11 = 0;
          }
          if ( v11 )
          {
            v30 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
          }
        }
      }
    }
    else
    {
      v6 = -2147024882;
    }
  }
  else
  {
    v5 = 0;
    v6 = -2147024809;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 128));
  if ( v6 >= 0 && *(_QWORD *)(a1 + 88) == -1 )
    v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 64LL))(a1, 1);
  *(_DWORD *)(a1 + 252) += DWORD2(v32);
  *(_DWORD *)(a1 + 272) += HIDWORD(v33);
  *(_DWORD *)(a1 + 276) += LODWORD(v34[0]);
  *(_DWORD *)(a1 + 280) += DWORD1(v34[0]);
  *(_DWORD *)(a1 + 284) += DWORD2(v34[0]);
  *(_DWORD *)(a1 + 288) += HIDWORD(v34[0]);
  *(_DWORD *)(a1 + 292) += LODWORD(v34[1]);
  *(_DWORD *)(a1 + 296) += DWORD1(v34[1]);
  *(_DWORD *)(a1 + 300) |= DWORD2(v34[1]);
  if ( v6 >= 0 )
  {
    if ( *(_QWORD *)(a1 + 168) || (unsigned int)InjectPointerInput(*(_QWORD *)(a1 + 88), v5, (unsigned int)v4) )
      goto LABEL_57;
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
LABEL_57:
      *(_DWORD *)(a1 + 264) += v4;
  }
  ++*(_DWORD *)(a1 + 244);
  if ( v6 < 0 )
  {
    ++*(_DWORD *)(a1 + 248);
    *(_DWORD *)(a1 + 260) = v6;
  }
  CoTaskMemFree(v5);
  if ( a1 != -128 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 128));
  v27 = v31;
  if ( v31 )
  {
    v31 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000c440  mov     rax, rsp
0x18000c443  mov     [rax+18h], rbx
0x18000c447  push    rbp
0x18000c448  push    rsi
0x18000c449  push    rdi
0x18000c44a  push    r12
0x18000c44c  push    r14
0x18000c44e  lea     rbp, [rax-5Fh]
0x18000c452  sub     rsp, 0B0h
0x18000c459  movaps  xmmword ptr [rax-38h], xmm6
0x18000c45d  mov     rax, cs:__security_cookie
0x18000c464  xor     rax, rsp
0x18000c467  mov     [rbp+57h+var_38], rax
0x18000c46b  mov     r14, rdx
0x18000c46e  mov     rdi, rcx
0x18000c471  xor     r12d, r12d
0x18000c474  mov     [rbp+57h+var_A0], r12
0x18000c478  xorps   xmm0, xmm0
0x18000c47b  movups  [rbp+57h+var_98], xmm0
0x18000c47f  movups  [rbp+57h+var_88], xmm0
0x18000c483  movups  [rbp+57h+var_78], xmm0
0x18000c487  movups  [rbp+57h+var_78+0Ch], xmm0
0x18000c48b  test    rdx, rdx
0x18000c48e  jnz     short loc_18000C49C
0x18000c490  xor     esi, esi
0x18000c492  mov     ebx, 80070057h
0x18000c497  jmp     loc_18000C779
0x18000c49c  mov     ebx, 9768h
0x18000c4a1  mov     ecx, ebx; cb
0x18000c4a3  call    cs:__imp_CoTaskMemAlloc
0x18000c4a9  mov     rsi, rax
0x18000c4ac  test    rax, rax
0x18000c4af  jnz     short loc_18000C4BB
0x18000c4b1  mov     ebx, 8007000Eh
0x18000c4b6  jmp     loc_18000C779
0x18000c4bb  mov     [rax], r12b
0x18000c4be  inc     rax
0x18000c4c1  sub     rbx, 1
0x18000c4c5  jnz     short loc_18000C4BB
0x18000c4c7  mov     rax, [r14]
0x18000c4ca  mov     rbx, [rax+30h]
0x18000c4ce  mov     rcx, [rbp+57h+var_A0]
0x18000c4d2  test    rcx, rcx
0x18000c4d5  jz      short loc_18000C4EC
0x18000c4d7  mov     [rbp+57h+var_A0], 0
0x18000c4df  mov     rdx, [rcx]
0x18000c4e2  mov     rax, [rdx+10h]
0x18000c4e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4eb  nop
0x18000c4ec  lea     rdx, [rbp+57h+var_A0]
0x18000c4f0  mov     rcx, r14
0x18000c4f3  mov     rax, rbx
0x18000c4f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4fb  mov     ebx, eax
0x18000c4fd  test    eax, eax
0x18000c4ff  js      loc_18000C779
0x18000c505  mov     [rbp+57h+var_B0], 0
0x18000c509  mov     rcx, [rbp+57h+var_A0]
0x18000c50d  mov     rax, [rcx]
0x18000c510  lea     rdx, [rbp+57h+var_B0]
0x18000c514  mov     rax, [rax+38h]
0x18000c518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c51d  mov     ebx, eax
0x18000c51f  test    eax, eax
0x18000c521  js      loc_18000C779
0x18000c527  xorps   xmm6, xmm6
0x18000c52a  cmp     [rbp+57h+var_B0], 0
0x18000c52e  jz      loc_18000C779
0x18000c534  cmp     r12d, 0FFh
0x18000c53b  jl      short loc_18000C54C
0x18000c53d  mov     ebx, 80070057h
0x18000c542  inc     dword ptr [rbp+57h+var_98+8]
0x18000c545  xor     ecx, ecx
0x18000c547  jmp     loc_18000C757
0x18000c54c  mov     [rbp+57h+var_A8], 0
0x18000c554  mov     rcx, [rbp+57h+var_A0]
0x18000c558  mov     rax, [rcx]
0x18000c55b  lea     rdx, [rbp+57h+var_A8]
0x18000c55f  mov     rax, [rax+30h]
0x18000c563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c568  mov     ebx, eax
0x18000c56a  mov     rcx, [rbp+57h+var_A8]
0x18000c56e  test    rcx, rcx
0x18000c571  jnz     short loc_18000C57D
0x18000c573  mov     ebx, 80070057h
0x18000c578  jmp     loc_18000C757
0x18000c57d  test    eax, eax
0x18000c57f  js      loc_18000C757
0x18000c585  movsxd  rax, r12d
0x18000c588  imul    r14, rax, 98h
0x18000c58f  mov     eax, 2
0x18000c594  mov     [r14+rsi], eax
0x18000c598  mov     [r14+rsi+8], eax
0x18000c59d  xorps   xmm0, xmm0
0x18000c5a0  movups  [rbp+57h+var_58], xmm0
0x18000c5a4  mov     rax, [rcx]
0x18000c5a7  lea     rdx, [rbp+57h+var_58]
0x18000c5ab  mov     rax, [rax+30h]
0x18000c5af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5b4  mov     ebx, eax
0x18000c5b6  test    eax, eax
0x18000c5b8  js      loc_18000C753
0x18000c5be  mov     eax, dword ptr [rbp+57h+var_58+4]
0x18000c5c1  mov     [r14+rsi+74h], eax
0x18000c5c6  mov     ecx, dword ptr [rbp+57h+var_58]
0x18000c5c9  mov     [r14+rsi+70h], ecx
0x18000c5ce  mov     edx, dword ptr [rbp+57h+var_58+8]
0x18000c5d1  mov     [r14+rsi+7Ch], edx
0x18000c5d6  mov     r8d, dword ptr [rbp+57h+var_58+0Ch]
0x18000c5da  mov     [r14+rsi+78h], r8d
0x18000c5df  test    eax, eax
0x18000c5e1  jnz     short loc_18000C5F0
0x18000c5e3  test    ecx, ecx
0x18000c5e5  jnz     short loc_18000C5F0
0x18000c5e7  test    edx, edx
0x18000c5e9  jnz     short loc_18000C5F0
0x18000c5eb  test    r8d, r8d
0x18000c5ee  jz      short loc_18000C5F3
0x18000c5f0  inc     dword ptr [rbp+57h+var_88+0Ch]
0x18000c5f3  mov     dword ptr [rbp+57h+var_58], 0
0x18000c5fa  mov     rcx, [rbp+57h+var_A8]
0x18000c5fe  mov     rax, [rcx]
0x18000c601  lea     rdx, [rbp+57h+var_58]
0x18000c605  mov     rax, [rax+40h]
0x18000c609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c60e  mov     ebx, eax
0x18000c610  test    eax, eax
0x18000c612  js      loc_18000C753
0x18000c618  mov     eax, dword ptr [rbp+57h+var_58]
0x18000c61b  mov     [r14+rsi+90h], eax
0x18000c623  test    eax, eax
0x18000c625  jz      short loc_18000C62A
0x18000c627  inc     dword ptr [rbp+57h+var_78]
0x18000c62a  xorps   xmm0, xmm0
0x18000c62d  movups  [rbp+57h+var_58], xmm0
0x18000c631  movups  [rbp+57h+var_48], xmm0
0x18000c635  mov     rcx, [rbp+57h+var_A8]
0x18000c639  mov     rax, [rcx]
0x18000c63c  lea     rdx, [rbp+57h+var_58]
0x18000c640  mov     rax, [rax+50h]
0x18000c644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c649  mov     ebx, eax
0x18000c64b  test    eax, eax
0x18000c64d  js      loc_18000C753
0x18000c653  mov     edx, dword ptr [rbp+57h+var_58]
0x18000c656  mov     r9d, dword ptr [rbp+57h+var_58+4]
0x18000c65a  mov     r8d, dword ptr [rbp+57h+var_58+8]
0x18000c65e  mov     ecx, dword ptr [rbp+57h+var_58+0Ch]
0x18000c661  mov     r10d, dword ptr [rbp+57h+var_48]
0x18000c665  mov     rax, qword ptr [rbp+57h+var_48+8]
0x18000c669  mov     [r14+rsi+58h], rax
0x18000c66e  test    rax, rax
0x18000c671  jz      short loc_18000C676
0x18000c673  inc     [rbp+57h+var_64]
0x18000c676  mov     [r14+rsi+28h], r8d
0x18000c67b  mov     [r14+rsi+2Ch], ecx
0x18000c680  or      ecx, r8d
0x18000c683  jle     short loc_18000C688
0x18000c685  inc     dword ptr [rbp+57h+var_78+0Ch]
0x18000c688  mov     [r14+rsi+0Ch], edx
0x18000c68d  test    edx, edx
0x18000c68f  jz      short loc_18000C694
0x18000c691  inc     dword ptr [rbp+57h+var_78+8]
0x18000c694  mov     [r14+rsi+14h], r9d
0x18000c699  or      [rbp+57h+var_60], r9d
0x18000c69d  mov     [r14+rsi+48h], r10d
0x18000c6a2  test    r10d, r10d
0x18000c6a5  jz      short loc_18000C6AA
0x18000c6a7  inc     [rbp+57h+var_68]
0x18000c6aa  movsd   qword ptr [rbp+57h+var_58], xmm6
0x18000c6af  mov     rcx, [rbp+57h+var_A8]
0x18000c6b3  mov     rax, [rcx]
0x18000c6b6  lea     rdx, [rbp+57h+var_58]
0x18000c6ba  mov     rax, [rax+60h]
0x18000c6be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6c3  mov     ebx, eax
0x18000c6c5  test    eax, eax
0x18000c6c7  js      loc_18000C753
0x18000c6cd  movsd   xmm1, qword ptr [rbp+57h+var_58]
0x18000c6d2  comisd  xmm1, cs:__real@3ff0000000000000
0x18000c6da  ja      short loc_18000C6FD
0x18000c6dc  comisd  xmm6, xmm1
0x18000c6e0  ja      short loc_18000C6FD
0x18000c6e2  xor     ebx, ebx
0x18000c6e4  movaps  xmm0, xmm1
0x18000c6e7  mulsd   xmm0, cs:__real@4090000000000000
0x18000c6ef  cvttsd2si eax, xmm0
0x18000c6f3  mov     [r14+rsi+94h], eax
0x18000c6fb  jmp     short loc_18000C702
0x18000c6fd  mov     ebx, 80070057h
0x18000c702  ucomisd xmm6, xmm1
0x18000c706  jp      short loc_18000C70A
0x18000c708  jz      short loc_18000C70D
0x18000c70a  inc     dword ptr [rbp+57h+var_78+4]
0x18000c70d  test    ebx, ebx
0x18000c70f  js      short loc_18000C753
0x18000c711  mov     dword ptr [rbp+57h+var_58], 0
0x18000c718  mov     rcx, [rbp+57h+var_A8]
0x18000c71c  mov     rax, [rcx]
0x18000c71f  lea     rdx, [rbp+57h+var_58]
0x18000c723  mov     rax, [rax+70h]
0x18000c727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c72c  mov     ebx, eax
0x18000c72e  test    eax, eax
0x18000c730  js      short loc_18000C753
0x18000c732  mov     eax, dword ptr [rbp+57h+var_58]
0x18000c735  mov     [r14+rsi+6Ch], eax
0x18000c73a  mov     rcx, [rbp+57h+var_A0]
0x18000c73e  mov     rax, [rcx]
0x18000c741  lea     rdx, [rbp+57h+var_B0]
0x18000c745  mov     rax, [rax+40h]
0x18000c749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c74e  mov     ebx, eax
0x18000c750  inc     r12d
0x18000c753  mov     rcx, [rbp+57h+var_A8]
0x18000c757  test    rcx, rcx
0x18000c75a  jz      short loc_18000C771
0x18000c75c  mov     [rbp+57h+var_A8], 0
0x18000c764  mov     rax, [rcx]
0x18000c767  mov     rax, [rax+10h]
0x18000c76b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c770  nop
0x18000c771  test    ebx, ebx
0x18000c773  jns     loc_18000C52A
0x18000c779  lea     r14, [rdi+80h]
0x18000c780  mov     rcx, r14; lpCriticalSection
0x18000c783  call    cs:__imp_EnterCriticalSection
0x18000c789  test    ebx, ebx
0x18000c78b  js      short loc_18000C7AA
0x18000c78d  cmp     qword ptr [rdi+58h], 0FFFFFFFFFFFFFFFFh
0x18000c792  jnz     short loc_18000C7AA
0x18000c794  mov     rax, [rdi]
0x18000c797  mov     edx, 1
0x18000c79c  mov     rcx, rdi
0x18000c79f  mov     rax, [rax+40h]
0x18000c7a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7a8  mov     ebx, eax
0x18000c7aa  mov     eax, dword ptr [rbp+57h+var_98+8]
0x18000c7ad  add     [rdi+0FCh], eax
0x18000c7b3  mov     eax, dword ptr [rbp+57h+var_88+0Ch]
0x18000c7b6  add     [rdi+110h], eax
0x18000c7bc  mov     eax, dword ptr [rbp+57h+var_78]
0x18000c7bf  add     [rdi+114h], eax
0x18000c7c5  mov     eax, dword ptr [rbp+57h+var_78+4]
0x18000c7c8  add     [rdi+118h], eax
0x18000c7ce  mov     eax, dword ptr [rbp+57h+var_78+8]
0x18000c7d1  add     [rdi+11Ch], eax
0x18000c7d7  mov     eax, dword ptr [rbp+57h+var_78+0Ch]
0x18000c7da  add     [rdi+120h], eax
0x18000c7e0  mov     eax, [rbp+57h+var_68]
0x18000c7e3  add     [rdi+124h], eax
0x18000c7e9  mov     eax, [rbp+57h+var_64]
0x18000c7ec  add     [rdi+128h], eax
0x18000c7f2  mov     eax, [rbp+57h+var_60]
0x18000c7f5  or      [rdi+12Ch], eax
0x18000c7fb  test    ebx, ebx
0x18000c7fd  js      short loc_18000C83D
0x18000c7ff  cmp     qword ptr [rdi+0A8h], 0
0x18000c807  jnz     short loc_18000C836
0x18000c809  mov     r8d, r12d
0x18000c80c  mov     rdx, rsi
0x18000c80f  mov     rcx, [rdi+58h]
0x18000c813  call    cs:__imp_InjectPointerInput
0x18000c819  test    eax, eax
0x18000c81b  jnz     short loc_18000C836
0x18000c81d  call    cs:__imp_GetLastError
0x18000c823  mov     ebx, eax
0x18000c825  test    eax, eax
0x18000c827  jle     short loc_18000C832
0x18000c829  movzx   ebx, ax
0x18000c82c  or      ebx, 80070000h
0x18000c832  test    ebx, ebx
0x18000c834  js      short loc_18000C83D
0x18000c836  add     [rdi+108h], r12d
0x18000c83d  inc     dword ptr [rdi+0F4h]
0x18000c843  test    ebx, ebx
0x18000c845  jns     short loc_18000C853
0x18000c847  inc     dword ptr [rdi+0F8h]
0x18000c84d  mov     [rdi+104h], ebx
0x18000c853  mov     rcx, rsi; pv
0x18000c856  call    cs:__imp_CoTaskMemFree
0x18000c85c  test    r14, r14
0x18000c85f  jz      short loc_18000C86B
0x18000c861  mov     rcx, r14; lpCriticalSection
0x18000c864  call    cs:__imp_LeaveCriticalSection
0x18000c86a  nop
0x18000c86b  mov     rcx, [rbp+57h+var_A0]
0x18000c86f  test    rcx, rcx
0x18000c872  jz      short loc_18000C889
0x18000c874  mov     [rbp+57h+var_A0], 0
0x18000c87c  mov     rax, [rcx]
0x18000c87f  mov     rax, [rax+10h]
0x18000c883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c888  nop
0x18000c889  mov     eax, ebx
0x18000c88b  mov     rcx, [rbp+57h+var_38]
0x18000c88f  xor     rcx, rsp; StackCookie
0x18000c892  call    __security_check_cookie
0x18000c897  lea     r11, [rsp+0D0h+var_20]
0x18000c89f  mov     rbx, [r11+40h]
  ... truncated ...
```
