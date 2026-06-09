# WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::DoCrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3 *,int)

- ea: `0x180022820`
- end: `0x180022bc6`
- name: `?DoCrypt@?$CEncryption@$01V?$CCipherFeistel64@$0A@$0GD@$0FH@$0OH@$0BF@$0LC@$0LB@$0BN@$0N@$0DK@$0FJ@$0ID@$0BB@$0LD@$0OK@$0FA@$0BD@$0LL@$0MF@$0MH@$02$0EA@$0JO@$01$01$0PL@$0GM@$0KE@$0P@$0LK@$0EI@$0NL@$0BC@$09$0CK@$0LM@$0BO@$0GO@$0HK@$0DC@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$0A@$00$0BKGBKNDEJDGFEBEE@@2@UENCRYPTED_SEGMENT_DATA_CONST_3@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_3@5@@WarbirdRuntime@@CAJPEAUENCRYPTED_SEGMENT_DATA_CONST_3@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_3@2@H@Z`
- size: `934`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800205b0`
- `0x180024290`

## callees

- `0x1800017b0`
- `0x18001f500`
- `0x18001ff20`
- `0x180022820`
- `0x180023ed0`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022930`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800229ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022b7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022930`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800229ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022b7b`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180022916`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18002299b`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180022b61`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180022916`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18002299b`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180022b61`

## pseudocode

```c
__int64 __fastcall WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::DoCrypt(
        __int64 a1,
        __int64 a2,
        int a3)
{
  unsigned __int16 v3; // dx
  int v5; // r15d
  unsigned int v6; // esi
  __int64 v7; // rcx
  struct HINSTANCE__ *v8; // r12
  __int64 v9; // rbx
  unsigned __int64 v10; // rdi
  HANDLE CurrentThread; // rax
  BOOL v12; // r14d
  HANDLE v13; // rax
  __int64 v14; // r14
  unsigned __int16 v15; // r8
  unsigned int v16; // ecx
  HANDLE v17; // rax
  _BYTE v19[4]; // [rsp+48h] [rbp-29h] BYREF
  int v20; // [rsp+4Ch] [rbp-25h] BYREF
  LPVOID lpAddress; // [rsp+50h] [rbp-21h]
  SIZE_T dwSize; // [rsp+58h] [rbp-19h]
  __int64 v23; // [rsp+60h] [rbp-11h]
  int v24; // [rsp+68h] [rbp-9h]
  __int64 v25; // [rsp+70h] [rbp-1h]
  DWORD flOldProtect[2]; // [rsp+78h] [rbp+7h] BYREF
  _BYTE v27[16]; // [rsp+80h] [rbp+Fh] BYREF
  char v28; // [rsp+90h] [rbp+1Fh]

  v3 = *(_WORD *)&WarbirdRuntime::g_EncryptedSegmentConstData_14;
  v5 = 0;
  v6 = 0;
  v25 = 0;
  lpAddress = 0;
  dwSize = 0;
  v23 = 0;
  v24 = a3;
  *(_QWORD *)flOldProtect = 0;
  if ( *(_WORD *)&WarbirdRuntime::g_EncryptedSegmentConstData_14 )
  {
    do
    {
      if ( v5 < 0 )
        break;
      v7 = v6;
      v8 = (struct HINSTANCE__ *)((char *)&_ImageBase + v7 * 8 + 673860);
      v9 = qword_1800A4808[v7 + 8] & 0xFFFFFFF;
      v10 = (unsigned __int64)&_ImageBase + (*(_DWORD *)v8 & 0xFFFFFFF);
      if ( v10 < (unsigned __int64)lpAddress || v9 + v10 >= (unsigned __int64)lpAddress + dwSize )
      {
        if ( flOldProtect[0] )
        {
          WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(
            (WarbirdRuntime::AutoEnableDynamicCodeGen *)v27,
            v3);
          VirtualProtect(lpAddress, dwSize, flOldProtect[1] | 0x40000000, &flOldProtect[1]);
          flOldProtect[0] = 0;
          if ( v28 )
          {
            v20 = 0;
            CurrentThread = GetCurrentThread();
            ((void (__fastcall *)(HANDLE, __int64, int *, __int64))WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(
              CurrentThread,
              2,
              &v20,
              4);
          }
        }
        lpAddress = (LPVOID)(v10 & 0xFFFFFFFFFFFFF000uLL);
        dwSize = ((v10 + v9 + 4095) & 0xFFFFFFFFFFFFF000uLL) - (v10 & 0xFFFFFFFFFFFFF000uLL);
        WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(
          (WarbirdRuntime::AutoEnableDynamicCodeGen *)v27,
          v3);
        v12 = VirtualProtect(lpAddress, dwSize, 0x40000040u, &flOldProtect[1]);
        flOldProtect[0] = v12;
        if ( v28 )
        {
          v20 = 0;
          v13 = GetCurrentThread();
          ((void (__fastcall *)(HANDLE, __int64, int *, __int64))WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(
            v13,
            2,
            &v20,
            4);
        }
        v3 = *(_WORD *)&WarbirdRuntime::g_EncryptedSegmentConstData_14;
        if ( !v12 )
          goto LABEL_17;
      }
      if ( v10 + v23 )
      {
        v14 = 2LL * v6;
        v15 = *(_WORD *)&algn_1800AD574[v14];
        if ( a3 )
        {
          if ( (v15 & 4) == 0 )
          {
            v19[0] = 0;
            WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Encrypt(
              v10,
              v10 + v23,
              v9,
              0,
              *(_DWORD *)v8 & 0xFFFFFFF,
              (__int64)v19);
            v3 = *(_WORD *)&WarbirdRuntime::g_EncryptedSegmentConstData_14;
            *(_WORD *)&algn_1800AD574[v14] &= 0xE01Fu;
            *(_WORD *)&algn_1800AD574[v14] |= (unsigned __int16)(32 * v19[0]) | 4;
          }
        }
        else if ( (v15 & 4) != 0 )
        {
          v16 = v15;
          LOWORD(v16) = ~v15;
          WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Decrypt(
            v10,
            v10 + v23,
            v9,
            0,
            *(_DWORD *)v8 & 0xFFFFFFF,
            v15 >> 5,
            (v16 >> 1) & 1);
          v3 = *(_WORD *)&WarbirdRuntime::g_EncryptedSegmentConstData_14;
          *(_WORD *)&algn_1800AD574[v14] = *(_WORD *)&algn_1800AD574[v14] & 0xFFF9 | 2;
        }
      }
      else
      {
LABEL_17:
        v5 = -2147024882;
      }
      ++v6;
    }
    while ( v6 < v3 );
    if ( flOldProtect[0] )
    {
      WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(
        (WarbirdRuntime::AutoEnableDynamicCodeGen *)v27,
        v3);
      VirtualProtect(lpAddress, dwSize, flOldProtect[1] | 0x40000000, &flOldProtect[1]);
      flOldProtect[0] = 0;
      if ( v28 )
      {
        v20 = 0;
        v17 = GetCurrentThread();
        ((void (__fastcall *)(HANDLE, __int64, int *, __int64))WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(
          v17,
          2,
          &v20,
          4);
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180022820  mov     r11, rsp
0x180022823  push    rbp
0x180022824  push    rsi
0x180022825  push    r13
0x180022827  push    r14
0x180022829  push    r15
0x18002282b  lea     rbp, [r11-5Fh]
0x18002282f  sub     rsp, 0A0h
0x180022836  mov     rax, cs:__security_cookie
0x18002283d  xor     rax, rsp
0x180022840  mov     [rbp+57h+var_30], rax
0x180022844  mov     rax, cs:qword_1800A4800
0x18002284b  xor     r14d, r14d
0x18002284e  mov     rdx, cs:?g_EncryptedSegmentConstData_14@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_3@1@A; bool
0x180022855  mov     r13d, r8d
0x180022858  shr     rax, 1
0x18002285b  mov     r15d, r14d
0x18002285e  movzx   eax, al
0x180022861  mov     esi, r14d
0x180022864  mov     [rbp+57h+var_58], rax
0x180022868  mov     [rbp+57h+lpAddress], r14
0x18002286c  mov     [rbp+57h+dwSize], r14
0x180022870  mov     [rbp+57h+var_68], r14
0x180022874  mov     [rbp+57h+var_60], r8d
0x180022878  mov     qword ptr [rbp+57h+flOldProtect], r14
0x18002287c  test    dx, dx
0x18002287f  jz      loc_180022BA6
0x180022885  mov     r9, cs:qword_1800A47F8
0x18002288c  lea     r8, __ImageBase
0x180022893  mov     [r11+8], rbx
0x180022897  mov     [r11+10h], rdi
0x18002289b  mov     [r11+18h], r12
0x18002289f  nop
0x1800228a0  test    r15d, r15d
0x1800228a3  js      loc_180022B25
0x1800228a9  mov     eax, esi
0x1800228ab  lea     rcx, ds:0[rax*8]
0x1800228b3  mov     ebx, [rcx+r8+0A4848h]
0x1800228bb  lea     r12, [rcx+0A4844h]
0x1800228c2  mov     rcx, [rbp+57h+lpAddress]
0x1800228c6  add     r12, r8
0x1800228c9  and     ebx, 0FFFFFFFh
0x1800228cf  mov     edi, [r12]
0x1800228d3  and     edi, 0FFFFFFFh
0x1800228d9  add     rdi, r8
0x1800228dc  cmp     rdi, rcx
0x1800228df  jb      short loc_1800228F2
0x1800228e1  add     rcx, [rbp+57h+dwSize]
0x1800228e5  lea     rax, [rbx+rdi]
0x1800228e9  cmp     rax, rcx
0x1800228ec  jb      loc_180022A03
0x1800228f2  cmp     [rbp+57h+flOldProtect], 0
0x1800228f6  jz      short loc_18002295B
0x1800228f8  lea     rcx, [rbp+57h+var_48]; this
0x1800228fc  call    ??0AutoEnableDynamicCodeGen@WarbirdRuntime@@QEAA@_N@Z; WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(bool)
0x180022901  mov     r8d, [rbp+57h+flOldProtect+4]
0x180022905  lea     r9, [rbp+57h+flOldProtect+4]; lpflOldProtect
0x180022909  mov     rdx, [rbp+57h+dwSize]; dwSize
0x18002290d  bts     r8d, 1Eh; flNewProtect
0x180022912  mov     rcx, [rbp+57h+lpAddress]; lpAddress
0x180022916  call    cs:__imp_VirtualProtect
0x18002291d  nop     dword ptr [rax+rax+00h]
0x180022922  cmp     [rbp+57h+var_38], 0
0x180022926  mov     [rbp+57h+flOldProtect], r14d
0x18002292a  jz      short loc_18002295B
0x18002292c  mov     [rbp+57h+var_7C], r14d
0x180022930  call    cs:__imp_GetCurrentThread
0x180022937  nop     dword ptr [rax+rax+00h]
0x18002293c  mov     r9d, 4
0x180022942  lea     r8, [rbp+57h+var_7C]
0x180022946  mov     rcx, rax
0x180022949  mov     edx, 2
0x18002294e  mov     rax, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x180022955  call    cs:__guard_dispatch_icall_fptr
0x18002295b  lea     rax, [rbx+0FFFh]
0x180022962  mov     rcx, rdi
0x180022965  and     rcx, 0FFFFFFFFFFFFF000h
0x18002296c  add     rax, rdi
0x18002296f  and     rax, 0FFFFFFFFFFFFF000h
0x180022975  mov     [rbp+57h+lpAddress], rcx
0x180022979  sub     rax, rcx
0x18002297c  lea     rcx, [rbp+57h+var_48]; this
0x180022980  mov     [rbp+57h+dwSize], rax
0x180022984  call    ??0AutoEnableDynamicCodeGen@WarbirdRuntime@@QEAA@_N@Z; WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(bool)
0x180022989  mov     rdx, [rbp+57h+dwSize]; dwSize
0x18002298d  lea     r9, [rbp+57h+flOldProtect+4]; lpflOldProtect
0x180022991  mov     rcx, [rbp+57h+lpAddress]; lpAddress
0x180022995  mov     r8d, 40000040h; flNewProtect
0x18002299b  call    cs:__imp_VirtualProtect
0x1800229a2  nop     dword ptr [rax+rax+00h]
0x1800229a7  cmp     [rbp+57h+var_38], 0
0x1800229ab  mov     r14d, eax
0x1800229ae  mov     [rbp+57h+flOldProtect], eax
0x1800229b1  jz      short loc_1800229E5
0x1800229b3  mov     [rbp+57h+var_7C], 0
0x1800229ba  call    cs:__imp_GetCurrentThread
0x1800229c1  nop     dword ptr [rax+rax+00h]
0x1800229c6  mov     r9d, 4
0x1800229cc  lea     r8, [rbp+57h+var_7C]
0x1800229d0  mov     rcx, rax
0x1800229d3  mov     edx, 2
0x1800229d8  mov     rax, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x1800229df  call    cs:__guard_dispatch_icall_fptr
0x1800229e5  mov     r9, cs:qword_1800A47F8
0x1800229ec  mov     rdx, cs:?g_EncryptedSegmentConstData_14@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_3@1@A; bool
0x1800229f3  test    r14d, r14d
0x1800229f6  jz      loc_180022B05
0x1800229fc  lea     r8, __ImageBase
0x180022a03  mov     r10, [rbp+57h+var_68]
0x180022a07  add     r10, rdi
0x180022a0a  jz      loc_180022B05
0x180022a10  mov     eax, esi
0x180022a12  lea     r14, [rax+rax]
0x180022a16  movzx   r8d, word ptr [r14+r8+0AD574h]
0x180022a1f  movzx   eax, r8w
0x180022a23  and     ax, 4
0x180022a27  test    r13d, r13d
0x180022a2a  jz      short loc_180022A96
0x180022a2c  test    ax, ax
0x180022a2f  jnz     loc_180022B0B
0x180022a35  mov     [rbp+57h+var_80], al
0x180022a38  lea     rcx, [rbp+57h+var_80]
0x180022a3c  mov     eax, [r12]
0x180022a40  mov     r8, rbx
0x180022a43  mov     qword ptr [rsp+0C0h+var_98], rcx
0x180022a48  and     eax, 0FFFFFFFh
0x180022a4d  mov     rdx, r10
0x180022a50  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180022a54  mov     rcx, rdi
0x180022a57  call    ?Encrypt@?$CEncryption@$01V?$CCipherFeistel64@$0A@$0GD@$0FH@$0OH@$0BF@$0LC@$0LB@$0BN@$0N@$0DK@$0FJ@$0ID@$0BB@$0LD@$0OK@$0FA@$0BD@$0LL@$0MF@$0MH@$02$0EA@$0JO@$01$01$0PL@$0GM@$0KE@$0P@$0LK@$0EI@$0NL@$0BC@$09$0CK@$0LM@$0BO@$0GO@$0HK@$0DC@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$0A@$00$0BKGBKNDEJDGFEBEE@@2@UENCRYPTED_SEGMENT_DATA_CONST_3@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_3@5@@WarbirdRuntime@@CAXPEBEPEAE_KTCKey@WarbirdCrypto@@K1@Z; WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Encrypt(uchar const *,uchar *,unsigned __int64,WarbirdCrypto::CKey,ulong,uchar *)
0x180022a5c  mov     r9, cs:qword_1800A47F8
0x180022a63  lea     r8, __ImageBase
0x180022a6a  mov     rdx, cs:?g_EncryptedSegmentConstData_14@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_3@1@A; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3 WarbirdRuntime::g_EncryptedSegmentConstData_14
0x180022a71  mov     eax, 0E01Fh
0x180022a76  and     [r14+r8+0AD574h], ax
0x180022a7f  movzx   eax, [rbp+57h+var_80]
0x180022a83  shl     ax, 5
0x180022a87  or      ax, 4
0x180022a8b  or      [r14+r8+0AD574h], ax
0x180022a94  jmp     short loc_180022B12
0x180022a96  test    ax, ax
0x180022a99  jz      short loc_180022B0B
0x180022a9b  mov     eax, [r12]
0x180022a9f  movzx   ecx, r8w
0x180022aa3  not     cx
0x180022aa6  shr     r8w, 5
0x180022aab  shr     ecx, 1
0x180022aad  and     eax, 0FFFFFFFh
0x180022ab2  and     ecx, 1
0x180022ab5  mov     rdx, r10
0x180022ab8  mov     [rsp+30h], ecx
0x180022abc  mov     rcx, rdi
0x180022abf  mov     byte ptr [rsp+0C0h+var_98], r8b
0x180022ac4  mov     r8, rbx
0x180022ac7  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180022acb  call    ?Decrypt@?$CEncryption@$01V?$CCipherFeistel64@$0A@$0GD@$0FH@$0OH@$0BF@$0LC@$0LB@$0BN@$0N@$0DK@$0FJ@$0ID@$0BB@$0LD@$0OK@$0FA@$0BD@$0LL@$0MF@$0MH@$02$0EA@$0JO@$01$01$0PL@$0GM@$0KE@$0P@$0LK@$0EI@$0NL@$0BC@$09$0CK@$0LM@$0BO@$0GO@$0HK@$0DC@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$0A@$00$0BKGBKNDEJDGFEBEE@@2@UENCRYPTED_SEGMENT_DATA_CONST_3@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_3@5@@WarbirdRuntime@@CAXPEBEPEAE_KTCKey@WarbirdCrypto@@KEH@Z; WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Decrypt(uchar const *,uchar *,unsigned __int64,WarbirdCrypto::CKey,ulong,uchar,int)
0x180022ad0  mov     r9, cs:qword_1800A47F8
0x180022ad7  lea     r8, __ImageBase
0x180022ade  movzx   eax, word ptr [r14+r8+0AD574h]
0x180022ae7  mov     ecx, 0FFFBh
0x180022aec  mov     rdx, cs:?g_EncryptedSegmentConstData_14@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_3@1@A; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3 WarbirdRuntime::g_EncryptedSegmentConstData_14
0x180022af3  and     ax, cx
0x180022af6  or      ax, 2
0x180022afa  mov     [r14+r8+0AD574h], ax
0x180022b03  jmp     short loc_180022B12
0x180022b05  mov     r15d, 8007000Eh
0x180022b0b  lea     r8, __ImageBase
0x180022b12  inc     esi
0x180022b14  movzx   eax, dx
0x180022b17  mov     r14d, 0
0x180022b1d  cmp     esi, eax
0x180022b1f  jb      loc_1800228A0
0x180022b25  cmp     [rbp+57h+flOldProtect], 0
0x180022b29  mov     r12, [rsp+0C0h+arg_10]
0x180022b31  mov     rdi, [rsp+0C0h+arg_8]
0x180022b39  mov     rbx, [rsp+0C0h+arg_0]
0x180022b41  jz      short loc_180022BA6
0x180022b43  lea     rcx, [rbp+57h+var_48]; this
0x180022b47  call    ??0AutoEnableDynamicCodeGen@WarbirdRuntime@@QEAA@_N@Z; WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(bool)
0x180022b4c  mov     r8d, [rbp+57h+flOldProtect+4]
0x180022b50  lea     r9, [rbp+57h+flOldProtect+4]; lpflOldProtect
0x180022b54  mov     rdx, [rbp+57h+dwSize]; dwSize
0x180022b58  bts     r8d, 1Eh; flNewProtect
0x180022b5d  mov     rcx, [rbp+57h+lpAddress]; lpAddress
0x180022b61  call    cs:__imp_VirtualProtect
0x180022b68  nop     dword ptr [rax+rax+00h]
0x180022b6d  cmp     [rbp+57h+var_38], 0
0x180022b71  mov     [rbp+57h+flOldProtect], r14d
0x180022b75  jz      short loc_180022BA6
0x180022b77  mov     [rbp+57h+var_7C], r14d
0x180022b7b  call    cs:__imp_GetCurrentThread
0x180022b82  nop     dword ptr [rax+rax+00h]
0x180022b87  mov     r9d, 4
0x180022b8d  lea     r8, [rbp+57h+var_7C]
0x180022b91  mov     rcx, rax
0x180022b94  mov     edx, 2
0x180022b99  mov     rax, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x180022ba0  call    cs:__guard_dispatch_icall_fptr
0x180022ba6  mov     eax, r15d
0x180022ba9  mov     rcx, [rbp+57h+var_30]
0x180022bad  xor     rcx, rsp; StackCookie
0x180022bb0  call    __security_check_cookie
0x180022bb5  add     rsp, 0A0h
0x180022bbc  pop     r15
0x180022bbe  pop     r14
0x180022bc0  pop     r13
0x180022bc2  pop     rsi
0x180022bc3  pop     rbp
0x180022bc4  retn
```
