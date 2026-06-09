# CsxManager::UpdateAdapterList(void)

- ea: `0x18000b11c`
- end: `0x18000b400`
- name: `?UpdateAdapterList@CsxManager@@QEAAXXZ`
- size: `740`
- prototype: `void __fastcall(CsxManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x18000a600`

## callees

- `0x1800016c0`
- `0x180001b6c`
- `0x180002188`
- `0x1800021fc`
- `0x180002b70`
- `0x18000a0d4`
- `0x18000b11c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b32a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b32a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b36e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b36e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000b320`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000b320`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000b3aa`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000b3aa`

## pseudocode

```c
void __fastcall CsxManager::UpdateAdapterList(CsxManager *this)
{
  __int64 v1; // rsi
  _QWORD *v2; // rdi
  _OWORD *v3; // rbx
  __int64 v4; // rbp
  __m128i v5; // xmm2
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  _DWORD *v8; // rax
  void *v9; // r14
  _DWORD *v10; // r8
  _QWORD *i; // rcx
  __int64 v12; // rdx
  int v13; // eax
  const struct std::nothrow_t *v14; // rdx
  unsigned int LastError; // ebx
  _QWORD *j; // rax
  _DWORD *v17; // rdx
  _QWORD *v18; // rcx
  _QWORD *v19; // rbx
  HANDLE hDevice; // [rsp+40h] [rbp-78h] BYREF
  __int128 v21; // [rsp+48h] [rbp-70h] BYREF
  unsigned int v22[8]; // [rsp+58h] [rbp-60h]

  v1 = 0;
  v2 = operator new(0x18u);
  *v2 = v2;
  v2[1] = v2;
  v3 = Src;
  v4 = qword_18001A2B0;
  if ( Src != (void *)qword_18001A2B0 )
  {
    do
    {
      v21 = *v3;
      *(_OWORD *)v22 = v3[1];
      v5 = *(__m128i *)((char *)v3 + 28);
      *(__m128i *)&v22[3] = v5;
      if ( *(_QWORD *)&v22[1] != __PAIR64__(v5.m128i_u32[0], v22[0])
        || _mm_cvtsi128_si32(_mm_srli_si128(v5, 4)) != _mm_cvtsi128_si32(_mm_srli_si128(v5, 8)) )
      {
        if ( v1 == 0xAAAAAAAAAAAAAAALL )
          std::_Xlength_error("list too long");
        v6 = operator new(0x18u);
        v6[2] = &v21;
        ++v1;
        v7 = (_QWORD *)v2[1];
        *v6 = v2;
        v6[1] = v7;
        v2[1] = v6;
        *v7 = v6;
      }
      v3 = (_OWORD *)((char *)v3 + 44);
    }
    while ( v3 != (_OWORD *)v4 );
    if ( v1 )
    {
      v8 = operator new[]((unsigned int)(16 * v1 + 8), (const struct std::nothrow_t *)&std::nothrow);
      v9 = v8;
      if ( v8 )
      {
        *v8 = -100597206;
        v8[1] = v1;
        v10 = v8 + 2;
        for ( i = (_QWORD *)*v2; i != v2; i = (_QWORD *)*i )
        {
          v12 = i[2];
          *v10 = *(_DWORD *)(v12 + 40);
          v10[2] = *(unsigned __int8 *)(v12 + 16);
          v10[3] = *(unsigned __int8 *)(v12 + 24);
          if ( *(_DWORD *)(v12 + 32) == 7 )
          {
            v13 = 2;
          }
          else if ( *(_DWORD *)(v12 + 32) == 8 )
          {
            v13 = 3;
          }
          else
          {
            v13 = 1;
          }
          v10[1] = v13;
          v10 += 4;
        }
        hDevice = 0;
        LastError = CxsOpenGIPhandle(&hDevice);
        if ( LastError )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              18,
              &WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids,
              LastError);
          }
        }
        else
        {
          if ( !DeviceIoControl(hDevice, 0x40001C24u, v9, 16 * v1 + 8, 0, 0, 0, 0) )
          {
            LastError = GetLastError();
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                19,
                &WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids,
                LastError);
            }
          }
          CloseHandle(hDevice);
        }
        operator delete(v9, v14);
        if ( !LastError )
        {
          for ( j = (_QWORD *)*v2; j != v2; j = (_QWORD *)*j )
          {
            v17 = (_DWORD *)j[2];
            v17[7] = v17[6];
            v17[5] = v17[4];
            v17[9] = v17[8];
          }
        }
      }
    }
  }
  *(_QWORD *)v2[1] = 0;
  v18 = (_QWORD *)*v2;
  if ( *v2 )
  {
    do
    {
      v19 = (_QWORD *)*v18;
      operator delete(v18, (const struct std::nothrow_t *)0x18);
      v18 = v19;
    }
    while ( v19 );
  }
  operator delete(v2, (const struct std::nothrow_t *)0x18);
}

```

## disassembly

```asm
0x18000b11c  push    rbx
0x18000b11e  push    rbp
0x18000b11f  push    rsi
0x18000b120  push    rdi
0x18000b121  push    r12
0x18000b123  push    r14
0x18000b125  sub     rsp, 88h
0x18000b12c  mov     rax, cs:__security_cookie
0x18000b133  xor     rax, rsp
0x18000b136  mov     [rsp+0B8h+var_40], rax
0x18000b13b  xor     esi, esi
0x18000b13d  lea     r12d, [rsi+18h]
0x18000b141  mov     ecx, r12d; Size
0x18000b144  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b149  mov     rdi, rax
0x18000b14c  mov     [rax], rax
0x18000b14f  mov     [rax+8], rax
0x18000b153  mov     rbx, cs:Src
0x18000b15a  mov     rbp, cs:qword_18001A2B0
0x18000b161  cmp     rbx, rbp
0x18000b164  jz      loc_18000B3B1
0x18000b16a  movups  xmm0, xmmword ptr [rbx]
0x18000b16d  movups  [rsp+0B8h+var_70], xmm0
0x18000b172  movups  xmm1, xmmword ptr [rbx+10h]
0x18000b176  movups  xmmword ptr [rsp+0B8h+var_60], xmm1
0x18000b17b  movups  xmm2, xmmword ptr [rbx+1Ch]
0x18000b17f  movups  xmmword ptr [rsp+0B8h+var_60+0Ch], xmm2
0x18000b184  mov     rax, qword ptr [rsp+0B8h+var_60+8]
0x18000b189  shr     rax, 20h
0x18000b18d  cmp     [rsp+0B8h+var_60+8], eax
0x18000b191  jnz     short loc_18000B1BC
0x18000b193  mov     rax, qword ptr [rsp+0B8h+var_60]
0x18000b198  shr     rax, 20h
0x18000b19c  cmp     [rsp+0B8h+var_60], eax
0x18000b1a0  jnz     short loc_18000B1BC
0x18000b1a2  movdqa  xmm0, xmm2
0x18000b1a6  psrldq  xmm0, 4
0x18000b1ab  movd    ecx, xmm0
0x18000b1af  psrldq  xmm2, 8
0x18000b1b4  movd    eax, xmm2
0x18000b1b8  cmp     ecx, eax
0x18000b1ba  jz      short loc_18000B1F5
0x18000b1bc  mov     rax, 0AAAAAAAAAAAAAAAh
0x18000b1c6  cmp     rsi, rax
0x18000b1c9  jz      loc_18000B3A3
0x18000b1cf  mov     rcx, r12; Size
0x18000b1d2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b1d7  lea     rcx, [rsp+0B8h+var_70]
0x18000b1dc  mov     [rax+10h], rcx
0x18000b1e0  inc     rsi
0x18000b1e3  mov     rcx, [rdi+8]
0x18000b1e7  mov     [rax], rdi
0x18000b1ea  mov     [rax+8], rcx
0x18000b1ee  mov     [rdi+8], rax
0x18000b1f2  mov     [rcx], rax
0x18000b1f5  add     rbx, 2Ch ; ','
0x18000b1f9  cmp     rbx, rbp
0x18000b1fc  jnz     loc_18000B16A
0x18000b202  test    rsi, rsi
0x18000b205  jz      loc_18000B3B1
0x18000b20b  mov     ebp, esi
0x18000b20d  shl     ebp, 4
0x18000b210  add     ebp, 8
0x18000b213  mov     ecx, ebp; unsigned __int64
0x18000b215  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b21c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000b221  mov     r14, rax
0x18000b224  test    rax, rax
0x18000b227  jz      loc_18000B3B1
0x18000b22d  mov     dword ptr [rax], 0FA01022Ah
0x18000b233  mov     [rax+4], esi
0x18000b236  lea     r8, [rax+8]
0x18000b23a  mov     rcx, [rdi]
0x18000b23d  cmp     rcx, rdi
0x18000b240  jz      short loc_18000B28C
0x18000b242  mov     rdx, [rcx+10h]
0x18000b246  mov     eax, [rdx+28h]
0x18000b249  mov     [r8], eax
0x18000b24c  movzx   eax, byte ptr [rdx+10h]
0x18000b250  mov     [r8+8], eax
0x18000b254  movzx   eax, byte ptr [rdx+18h]
0x18000b258  mov     [r8+0Ch], eax
0x18000b25c  mov     r9d, [rdx+20h]
0x18000b260  sub     r9d, 7
0x18000b264  jz      short loc_18000B27A
0x18000b266  cmp     r9d, 1
0x18000b26a  jz      short loc_18000B273
0x18000b26c  mov     eax, 1
0x18000b271  jmp     short loc_18000B27F
0x18000b273  mov     eax, 3
0x18000b278  jmp     short loc_18000B27F
0x18000b27a  mov     eax, 2
0x18000b27f  mov     [r8+4], eax
0x18000b283  add     r8, 10h
0x18000b287  mov     rcx, [rcx]
0x18000b28a  jmp     short loc_18000B23D
0x18000b28c  mov     [rsp+0B8h+hDevice], 0
0x18000b295  lea     rcx, [rsp+0B8h+hDevice]; void **
0x18000b29a  call    ?CxsOpenGIPhandle@@YAKPEAPEAX@Z; CxsOpenGIPhandle(void * *)
0x18000b29f  mov     ebx, eax
0x18000b2a1  test    eax, eax
0x18000b2a3  jz      short loc_18000B2ED
0x18000b2a5  lea     rax, WPP_GLOBAL_Control
0x18000b2ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2b3  cmp     rcx, rax
0x18000b2b6  jz      loc_18000B374
0x18000b2bc  test    byte ptr [rcx+1Ch], 4
0x18000b2c0  jz      loc_18000B374
0x18000b2c6  cmp     byte ptr [rcx+19h], 2
0x18000b2ca  jb      loc_18000B374
0x18000b2d0  mov     edx, 12h
0x18000b2d5  mov     r9d, ebx
0x18000b2d8  lea     r8, WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids
0x18000b2df  mov     rcx, [rcx+10h]
0x18000b2e3  call    WPP_SF_D
0x18000b2e8  jmp     loc_18000B374
0x18000b2ed  mov     [rsp+0B8h+lpOverlapped], 0; lpOverlapped
0x18000b2f6  mov     [rsp+0B8h+lpBytesReturned], 0; lpBytesReturned
0x18000b2ff  mov     [rsp+0B8h+nOutBufferSize], 0; nOutBufferSize
0x18000b307  mov     [rsp+0B8h+lpOutBuffer], 0; lpOutBuffer
0x18000b310  mov     r9d, ebp; nInBufferSize
0x18000b313  mov     r8, r14; lpInBuffer
0x18000b316  mov     edx, 40001C24h; dwIoControlCode
0x18000b31b  mov     rcx, [rsp+0B8h+hDevice]; hDevice
0x18000b320  call    cs:__imp_DeviceIoControl
0x18000b326  test    eax, eax
0x18000b328  jnz     short loc_18000B369
0x18000b32a  call    cs:__imp_GetLastError
0x18000b330  mov     ebx, eax
0x18000b332  lea     rax, WPP_GLOBAL_Control
0x18000b339  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b340  cmp     rcx, rax
0x18000b343  jz      short loc_18000B369
0x18000b345  test    byte ptr [rcx+1Ch], 4
0x18000b349  jz      short loc_18000B369
0x18000b34b  cmp     byte ptr [rcx+19h], 2
0x18000b34f  jb      short loc_18000B369
0x18000b351  mov     edx, 13h
0x18000b356  mov     r9d, ebx
0x18000b359  lea     r8, WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids
0x18000b360  mov     rcx, [rcx+10h]
0x18000b364  call    WPP_SF_D
0x18000b369  mov     rcx, [rsp+0B8h+hDevice]; hObject
0x18000b36e  call    cs:__imp_CloseHandle
0x18000b374  mov     rcx, r14; void *
0x18000b377  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b37c  test    ebx, ebx
0x18000b37e  jnz     short loc_18000B3B1
0x18000b380  mov     rax, [rdi]
0x18000b383  cmp     rax, rdi
0x18000b386  jz      short loc_18000B3B1
0x18000b388  mov     rdx, [rax+10h]
0x18000b38c  mov     ecx, [rdx+18h]
0x18000b38f  mov     [rdx+1Ch], ecx
0x18000b392  mov     ecx, [rdx+10h]
0x18000b395  mov     [rdx+14h], ecx
0x18000b398  mov     ecx, [rdx+20h]
0x18000b39b  mov     [rdx+24h], ecx
0x18000b39e  mov     rax, [rax]
0x18000b3a1  jmp     short loc_18000B383
0x18000b3a3  lea     rcx, aListTooLong; "list too long"
0x18000b3aa  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000b3b1  mov     rax, [rdi+8]
0x18000b3b5  mov     qword ptr [rax], 0
0x18000b3bc  mov     rcx, [rdi]; void *
0x18000b3bf  test    rcx, rcx
0x18000b3c2  jz      short loc_18000B3D7
0x18000b3c4  mov     rbx, [rcx]
0x18000b3c7  mov     rdx, r12; struct std::nothrow_t *
0x18000b3ca  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b3cf  mov     rcx, rbx
0x18000b3d2  test    rbx, rbx
0x18000b3d5  jnz     short loc_18000B3C4
0x18000b3d7  mov     rdx, r12; struct std::nothrow_t *
0x18000b3da  mov     rcx, rdi; void *
0x18000b3dd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b3e2  nop
0x18000b3e3  mov     rcx, [rsp+0B8h+var_40]
0x18000b3e8  xor     rcx, rsp; StackCookie
0x18000b3eb  call    __security_check_cookie
0x18000b3f0  add     rsp, 88h
0x18000b3f7  pop     r14
0x18000b3f9  pop     r12
0x18000b3fb  pop     rdi
0x18000b3fc  pop     rsi
0x18000b3fd  pop     rbp
0x18000b3fe  pop     rbx
0x18000b3ff  retn
```
