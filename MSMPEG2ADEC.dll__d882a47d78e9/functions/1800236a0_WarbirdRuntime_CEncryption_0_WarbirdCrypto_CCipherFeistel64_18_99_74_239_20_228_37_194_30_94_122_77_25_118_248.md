# WarbirdRuntime::CEncryption<0,WarbirdCrypto::CCipherFeistel64<18,99,74,239,20,228,37,194,30,94,122,77,25,118,248,234,22,247,37,157,1,4,13,20,8,127,8,216,11,29,81,74,10,231,117,28,2,213,211,86>,WarbirdCrypto::CHashFunctionSCP<2,3,0,-2057503231663003538>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1>::DoCrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1 *,int)

- ea: `0x1800236a0`
- end: `0x180023a63`
- name: `?DoCrypt@?$CEncryption@$0A@V?$CCipherFeistel64@$0BC@$0GD@$0EK@$0OP@$0BE@$0OE@$0CF@$0MC@$0BO@$0FO@$0HK@$0EN@$0BJ@$0HG@$0PI@$0OK@$0BG@$0PH@$0CF@$0JN@$00$03$0N@$0BE@$07$0HP@$07$0NI@$0L@$0BN@$0FB@$0EK@$09$0OH@$0HF@$0BM@$01$0NF@$0ND@$0FG@@WarbirdCrypto@@V?$CHashFunctionSCP@$01$02$0A@$0?BMINLIEJLPHNNHJC@@2@UENCRYPTED_SEGMENT_DATA_CONST_1@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_1@5@@WarbirdRuntime@@CAJPEAUENCRYPTED_SEGMENT_DATA_CONST_1@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_1@2@H@Z`
- size: `963`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180022130`
- `0x180024fd0`

## callees

- `0x1800017b0`
- `0x18001f500`
- `0x180021ab0`
- `0x1800236a0`
- `0x180024c00`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800237c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002384a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023a18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800237c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002384a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023a18`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800237a6`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18002382b`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800239fe`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800237a6`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18002382b`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800239fe`

## pseudocode

```c
__int64 __fastcall WarbirdRuntime::CEncryption<0,WarbirdCrypto::CCipherFeistel64<18,99,74,239,20,228,37,194,30,94,122,77,25,118,248,234,22,247,37,157,1,4,13,20,8,127,8,216,11,29,81,74,10,231,117,28,2,213,211,86>,WarbirdCrypto::CHashFunctionSCP<2,3,0,-2057503231663003538>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1>::DoCrypt(
        __int64 a1,
        __int64 a2,
        int a3)
{
  unsigned int v3; // edx
  int v5; // r15d
  unsigned int v6; // esi
  __int64 v7; // rbx
  struct HINSTANCE__ *v8; // r12
  __int64 v9; // rbx
  unsigned __int64 v10; // rdi
  HANDLE CurrentThread; // rax
  BOOL v12; // r14d
  HANDLE v13; // rax
  __int64 v14; // r14
  unsigned __int16 v15; // r8
  __int16 v16; // ax
  unsigned int v17; // ecx
  HANDLE v18; // rax
  _BYTE v20[4]; // [rsp+40h] [rbp-29h] BYREF
  int v21; // [rsp+44h] [rbp-25h] BYREF
  LPVOID lpAddress; // [rsp+48h] [rbp-21h]
  SIZE_T dwSize; // [rsp+50h] [rbp-19h]
  __int64 v24; // [rsp+58h] [rbp-11h]
  int v25; // [rsp+60h] [rbp-9h]
  __int64 v26; // [rsp+68h] [rbp-1h]
  DWORD flOldProtect[2]; // [rsp+70h] [rbp+7h] BYREF
  _BYTE v28[16]; // [rsp+78h] [rbp+Fh] BYREF
  char v29; // [rsp+88h] [rbp+1Fh]

  v3 = *(_DWORD *)&WarbirdRuntime::g_EncryptedSegmentConstData_3;
  lpAddress = 0;
  v5 = 0;
  v26 = (unsigned __int8)(*(_QWORD *)&WarbirdRuntime::g_EncryptedSegmentConstData_3 >> 17);
  v6 = 0;
  dwSize = 0;
  v24 = 0;
  v25 = a3;
  *(_QWORD *)flOldProtect = 0;
  if ( (*(_DWORD *)&WarbirdRuntime::g_EncryptedSegmentConstData_3 & 0x1FFFE) != 0 )
  {
    do
    {
      if ( v5 < 0 )
        break;
      v7 = v6;
      v8 = (struct HINSTANCE__ *)((char *)&_ImageBase + v7 * 8 + 673952);
      v9 = HIDWORD(qword_1800A4860[v7 + 8]) & 0xFFFFFFF;
      v10 = (unsigned __int64)&_ImageBase + (*(_DWORD *)v8 & 0xFFFFFFF);
      if ( v10 < (unsigned __int64)lpAddress || v9 + v10 >= (unsigned __int64)lpAddress + dwSize )
      {
        if ( flOldProtect[0] )
        {
          WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(
            (WarbirdRuntime::AutoEnableDynamicCodeGen *)v28,
            v3);
          VirtualProtect(lpAddress, dwSize, flOldProtect[1] | 0x40000000, &flOldProtect[1]);
          flOldProtect[0] = 0;
          if ( v29 )
          {
            v21 = 0;
            CurrentThread = GetCurrentThread();
            ((void (__fastcall *)(HANDLE, __int64, int *, __int64))WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(
              CurrentThread,
              2,
              &v21,
              4);
          }
        }
        lpAddress = (LPVOID)(v10 & 0xFFFFFFFFFFFFF000uLL);
        dwSize = ((v10 + v9 + 4095) & 0xFFFFFFFFFFFFF000uLL) - (v10 & 0xFFFFFFFFFFFFF000uLL);
        WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(
          (WarbirdRuntime::AutoEnableDynamicCodeGen *)v28,
          v3);
        v12 = VirtualProtect(lpAddress, dwSize, 0x40000040u, &flOldProtect[1]);
        flOldProtect[0] = v12;
        if ( v29 )
        {
          v21 = 0;
          v13 = GetCurrentThread();
          ((void (__fastcall *)(HANDLE, __int64, int *, __int64))WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(
            v13,
            2,
            &v21,
            4);
        }
        v3 = *(_DWORD *)&WarbirdRuntime::g_EncryptedSegmentConstData_3;
        if ( !v12 )
          goto LABEL_17;
      }
      if ( v10 + v24 )
      {
        v14 = 2LL * v6;
        v15 = *(_WORD *)&algn_1800AD57C[v14];
        v16 = v15 & 0x800;
        if ( a3 )
        {
          if ( !v16 )
          {
            v20[0] = 0;
            WarbirdRuntime::CEncryption<0,WarbirdCrypto::CCipherFeistel64<18,99,74,239,20,228,37,194,30,94,122,77,25,118,248,234,22,247,37,157,1,4,13,20,8,127,8,216,11,29,81,74,10,231,117,28,2,213,211,86>,WarbirdCrypto::CHashFunctionSCP<2,3,0,-2057503231663003538>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1>::Encrypt(
              v10,
              v10 + v24,
              v9,
              0,
              *(_DWORD *)v8 & 0xFFFFFFF,
              (__int64)v20);
            v3 = *(_DWORD *)&WarbirdRuntime::g_EncryptedSegmentConstData_3;
            algn_1800AD57C[v14] = v20[0];
            *(_WORD *)&algn_1800AD57C[v14] |= 0x800u;
          }
        }
        else if ( v16 )
        {
          v17 = v15;
          LOWORD(v17) = ~v15;
          WarbirdRuntime::CEncryption<0,WarbirdCrypto::CCipherFeistel64<18,99,74,239,20,228,37,194,30,94,122,77,25,118,248,234,22,247,37,157,1,4,13,20,8,127,8,216,11,29,81,74,10,231,117,28,2,213,211,86>,WarbirdCrypto::CHashFunctionSCP<2,3,0,-2057503231663003538>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1>::Decrypt(
            v10,
            v10 + v24,
            v9,
            0,
            *(_DWORD *)v8 & 0xFFFFFFF,
            v15,
            (v17 >> 13) & 1);
          v3 = *(_DWORD *)&WarbirdRuntime::g_EncryptedSegmentConstData_3;
          *(_WORD *)&algn_1800AD57C[v14] = *(_WORD *)&algn_1800AD57C[v14] & 0xD7FF | 0x2000;
        }
      }
      else
      {
LABEL_17:
        v5 = -2147024882;
      }
      ++v6;
    }
    while ( v6 < (unsigned __int16)(v3 >> 1) );
    if ( flOldProtect[0] )
    {
      WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(
        (WarbirdRuntime::AutoEnableDynamicCodeGen *)v28,
        v3);
      VirtualProtect(lpAddress, dwSize, flOldProtect[1] | 0x40000000, &flOldProtect[1]);
      flOldProtect[0] = 0;
      if ( v29 )
      {
        v21 = 0;
        v18 = GetCurrentThread();
        ((void (__fastcall *)(HANDLE, __int64, int *, __int64))WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(
          v18,
          2,
          &v21,
          4);
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800236a0  push    rbp
0x1800236a2  push    rsi
0x1800236a3  push    r13
0x1800236a5  push    r14
0x1800236a7  push    r15
0x1800236a9  lea     rbp, [rsp-37h]
0x1800236ae  sub     rsp, 0A0h
0x1800236b5  mov     rax, cs:__security_cookie
0x1800236bc  xor     rax, rsp
0x1800236bf  mov     [rbp+57h+var_30], rax
0x1800236c3  mov     rdx, cs:?g_EncryptedSegmentConstData_3@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_1@1@A; bool
0x1800236ca  xor     r14d, r14d
0x1800236cd  mov     rax, rdx
0x1800236d0  mov     [rbp+57h+lpAddress], r14
0x1800236d4  shr     rax, 11h
0x1800236d8  mov     r13d, r8d
0x1800236db  movzx   eax, al
0x1800236de  mov     r15d, r14d
0x1800236e1  mov     [rbp+57h+var_58], rax
0x1800236e5  mov     esi, r14d
0x1800236e8  mov     [rbp+57h+dwSize], r14
0x1800236ec  mov     [rbp+57h+var_68], r14
0x1800236f0  mov     [rbp+57h+var_60], r8d
0x1800236f4  mov     qword ptr [rbp+57h+flOldProtect], r14
0x1800236f8  test    edx, 1FFFEh
0x1800236fe  jbe     loc_180023A43
0x180023704  mov     r9, cs:qword_1800A4858
0x18002370b  lea     r8, __ImageBase
0x180023712  mov     [rsp+0C0h+arg_0], rbx
0x18002371a  mov     r11d, 800h
0x180023720  mov     [rsp+0C0h+arg_8], rdi
0x180023728  mov     [rsp+0C0h+arg_10], r12
0x180023730  test    r15d, r15d
0x180023733  js      loc_1800239C2
0x180023739  mov     rcx, [rbp+57h+lpAddress]
0x18002373d  mov     eax, esi
0x18002373f  lea     rbx, ds:0[rax*8]
0x180023747  lea     r12, [rbx+0A48A0h]
0x18002374e  mov     ebx, [rbx+r8+0A48A4h]
0x180023756  add     r12, r8
0x180023759  and     ebx, 0FFFFFFFh
0x18002375f  mov     edi, [r12]
0x180023763  and     edi, 0FFFFFFFh
0x180023769  add     rdi, r8
0x18002376c  cmp     rdi, rcx
0x18002376f  jb      short loc_180023782
0x180023771  add     rcx, [rbp+57h+dwSize]
0x180023775  lea     rax, [rbx+rdi]
0x180023779  cmp     rax, rcx
0x18002377c  jb      loc_180023899
0x180023782  cmp     [rbp+57h+flOldProtect], 0
0x180023786  jz      short loc_1800237EB
0x180023788  lea     rcx, [rbp+57h+var_48]; this
0x18002378c  call    ??0AutoEnableDynamicCodeGen@WarbirdRuntime@@QEAA@_N@Z; WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(bool)
0x180023791  mov     r8d, [rbp+57h+flOldProtect+4]
0x180023795  lea     r9, [rbp+57h+flOldProtect+4]; lpflOldProtect
0x180023799  mov     rdx, [rbp+57h+dwSize]; dwSize
0x18002379d  bts     r8d, 1Eh; flNewProtect
0x1800237a2  mov     rcx, [rbp+57h+lpAddress]; lpAddress
0x1800237a6  call    cs:__imp_VirtualProtect
0x1800237ad  nop     dword ptr [rax+rax+00h]
0x1800237b2  cmp     [rbp+57h+var_38], 0
0x1800237b6  mov     [rbp+57h+flOldProtect], r14d
0x1800237ba  jz      short loc_1800237EB
0x1800237bc  mov     [rbp+57h+var_7C], r14d
0x1800237c0  call    cs:__imp_GetCurrentThread
0x1800237c7  nop     dword ptr [rax+rax+00h]
0x1800237cc  mov     r9d, 4
0x1800237d2  lea     r8, [rbp+57h+var_7C]
0x1800237d6  mov     rcx, rax
0x1800237d9  mov     edx, 2
0x1800237de  mov     rax, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x1800237e5  call    cs:__guard_dispatch_icall_fptr
0x1800237eb  lea     rax, [rbx+0FFFh]
0x1800237f2  mov     rcx, rdi
0x1800237f5  and     rcx, 0FFFFFFFFFFFFF000h
0x1800237fc  add     rax, rdi
0x1800237ff  and     rax, 0FFFFFFFFFFFFF000h
0x180023805  mov     [rbp+57h+lpAddress], rcx
0x180023809  sub     rax, rcx
0x18002380c  lea     rcx, [rbp+57h+var_48]; this
0x180023810  mov     [rbp+57h+dwSize], rax
0x180023814  call    ??0AutoEnableDynamicCodeGen@WarbirdRuntime@@QEAA@_N@Z; WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(bool)
0x180023819  mov     rdx, [rbp+57h+dwSize]; dwSize
0x18002381d  lea     r9, [rbp+57h+flOldProtect+4]; lpflOldProtect
0x180023821  mov     rcx, [rbp+57h+lpAddress]; lpAddress
0x180023825  mov     r8d, 40000040h; flNewProtect
0x18002382b  call    cs:__imp_VirtualProtect
0x180023832  nop     dword ptr [rax+rax+00h]
0x180023837  cmp     [rbp+57h+var_38], 0
0x18002383b  mov     r14d, eax
0x18002383e  mov     [rbp+57h+flOldProtect], eax
0x180023841  jz      short loc_180023875
0x180023843  mov     [rbp+57h+var_7C], 0
0x18002384a  call    cs:__imp_GetCurrentThread
0x180023851  nop     dword ptr [rax+rax+00h]
0x180023856  mov     r9d, 4
0x18002385c  lea     r8, [rbp+57h+var_7C]
0x180023860  mov     rcx, rax
0x180023863  mov     edx, 2
0x180023868  mov     rax, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x18002386f  call    cs:__guard_dispatch_icall_fptr
0x180023875  mov     r9, cs:qword_1800A4858
0x18002387c  mov     rdx, cs:?g_EncryptedSegmentConstData_3@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_1@1@A; bool
0x180023883  test    r14d, r14d
0x180023886  jz      loc_180023998
0x18002388c  lea     r8, __ImageBase
0x180023893  mov     r11d, 800h
0x180023899  mov     r10, [rbp+57h+var_68]
0x18002389d  add     r10, rdi
0x1800238a0  jz      loc_180023998
0x1800238a6  mov     eax, esi
0x1800238a8  lea     r14, [rax+rax]
0x1800238ac  movzx   r8d, word ptr [r14+r8+0AD57Ch]
0x1800238b5  movzx   eax, r8w
0x1800238b9  and     ax, r11w
0x1800238bd  test    r13d, r13d
0x1800238c0  jz      short loc_180023927
0x1800238c2  test    ax, ax
0x1800238c5  jnz     loc_1800239A4
0x1800238cb  mov     [rbp+57h+var_80], al
0x1800238ce  lea     rcx, [rbp+57h+var_80]
0x1800238d2  mov     eax, [r12]
0x1800238d6  mov     r8, rbx
0x1800238d9  mov     [rsp+0C0h+var_98], rcx
0x1800238de  and     eax, 0FFFFFFFh
0x1800238e3  mov     rdx, r10
0x1800238e6  mov     [rsp+0C0h+var_A0], eax
0x1800238ea  mov     rcx, rdi
0x1800238ed  call    ?Encrypt@?$CEncryption@$0A@V?$CCipherFeistel64@$0BC@$0GD@$0EK@$0OP@$0BE@$0OE@$0CF@$0MC@$0BO@$0FO@$0HK@$0EN@$0BJ@$0HG@$0PI@$0OK@$0BG@$0PH@$0CF@$0JN@$00$03$0N@$0BE@$07$0HP@$07$0NI@$0L@$0BN@$0FB@$0EK@$09$0OH@$0HF@$0BM@$01$0NF@$0ND@$0FG@@WarbirdCrypto@@V?$CHashFunctionSCP@$01$02$0A@$0?BMINLIEJLPHNNHJC@@2@UENCRYPTED_SEGMENT_DATA_CONST_1@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_1@5@@WarbirdRuntime@@CAXPEBEPEAE_KTCKey@WarbirdCrypto@@K1@Z; WarbirdRuntime::CEncryption<0,WarbirdCrypto::CCipherFeistel64<18,99,74,239,20,228,37,194,30,94,122,77,25,118,248,234,22,247,37,157,1,4,13,20,8,127,8,216,11,29,81,74,10,231,117,28,2,213,211,86>,WarbirdCrypto::CHashFunctionSCP<2,3,0,-2057503231663003538>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1>::Encrypt(uchar const *,uchar *,unsigned __int64,WarbirdCrypto::CKey,ulong,uchar *)
0x1800238f2  movzx   eax, [rbp+57h+var_80]
0x1800238f6  lea     r8, __ImageBase
0x1800238fd  mov     r9, cs:qword_1800A4858
0x180023904  mov     r11d, 800h
0x18002390a  mov     rdx, cs:?g_EncryptedSegmentConstData_3@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_1@1@A; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1 WarbirdRuntime::g_EncryptedSegmentConstData_3
0x180023911  mov     [r14+r8+0AD57Ch], al
0x180023919  or      [r14+r8+0AD57Ch], r11w
0x180023922  jmp     loc_1800239AB
0x180023927  test    ax, ax
0x18002392a  jz      short loc_1800239A4
0x18002392c  mov     eax, [r12]
0x180023930  movzx   ecx, r8w
0x180023934  not     cx
0x180023937  and     eax, 0FFFFFFFh
0x18002393c  shr     ecx, 0Dh
0x18002393f  mov     rdx, r10
0x180023942  and     ecx, 1
0x180023945  mov     [rsp+0C0h+var_90], ecx
0x180023949  mov     rcx, rdi
0x18002394c  mov     byte ptr [rsp+0C0h+var_98], r8b
0x180023951  mov     r8, rbx
0x180023954  mov     [rsp+0C0h+var_A0], eax
0x180023958  call    ?Decrypt@?$CEncryption@$0A@V?$CCipherFeistel64@$0BC@$0GD@$0EK@$0OP@$0BE@$0OE@$0CF@$0MC@$0BO@$0FO@$0HK@$0EN@$0BJ@$0HG@$0PI@$0OK@$0BG@$0PH@$0CF@$0JN@$00$03$0N@$0BE@$07$0HP@$07$0NI@$0L@$0BN@$0FB@$0EK@$09$0OH@$0HF@$0BM@$01$0NF@$0ND@$0FG@@WarbirdCrypto@@V?$CHashFunctionSCP@$01$02$0A@$0?BMINLIEJLPHNNHJC@@2@UENCRYPTED_SEGMENT_DATA_CONST_1@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_1@5@@WarbirdRuntime@@CAXPEBEPEAE_KTCKey@WarbirdCrypto@@KEH@Z; WarbirdRuntime::CEncryption<0,WarbirdCrypto::CCipherFeistel64<18,99,74,239,20,228,37,194,30,94,122,77,25,118,248,234,22,247,37,157,1,4,13,20,8,127,8,216,11,29,81,74,10,231,117,28,2,213,211,86>,WarbirdCrypto::CHashFunctionSCP<2,3,0,-2057503231663003538>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1>::Decrypt(uchar const *,uchar *,unsigned __int64,WarbirdCrypto::CKey,ulong,uchar,int)
0x18002395d  mov     r9, cs:qword_1800A4858
0x180023964  lea     r8, __ImageBase
0x18002396b  movzx   eax, word ptr [r14+r8+0AD57Ch]
0x180023974  mov     ecx, 0F7FFh
0x180023979  mov     rdx, cs:?g_EncryptedSegmentConstData_3@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_1@1@A; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1 WarbirdRuntime::g_EncryptedSegmentConstData_3
0x180023980  and     ax, cx
0x180023983  or      ax, 2000h
0x180023987  mov     r11d, 800h
0x18002398d  mov     [r14+r8+0AD57Ch], ax
0x180023996  jmp     short loc_1800239AB
0x180023998  mov     r15d, 8007000Eh
0x18002399e  mov     r11d, 800h
0x1800239a4  lea     r8, __ImageBase
0x1800239ab  mov     eax, edx
0x1800239ad  inc     esi
0x1800239af  shr     eax, 1
0x1800239b1  mov     r14d, 0
0x1800239b7  movzx   eax, ax
0x1800239ba  cmp     esi, eax
0x1800239bc  jb      loc_180023730
0x1800239c2  cmp     [rbp+57h+flOldProtect], 0
0x1800239c6  mov     r12, [rsp+0C0h+arg_10]
0x1800239ce  mov     rdi, [rsp+0C0h+arg_8]
0x1800239d6  mov     rbx, [rsp+0C0h+arg_0]
0x1800239de  jz      short loc_180023A43
0x1800239e0  lea     rcx, [rbp+57h+var_48]; this
0x1800239e4  call    ??0AutoEnableDynamicCodeGen@WarbirdRuntime@@QEAA@_N@Z; WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(bool)
0x1800239e9  mov     r8d, [rbp+57h+flOldProtect+4]
0x1800239ed  lea     r9, [rbp+57h+flOldProtect+4]; lpflOldProtect
0x1800239f1  mov     rdx, [rbp+57h+dwSize]; dwSize
0x1800239f5  bts     r8d, 1Eh; flNewProtect
0x1800239fa  mov     rcx, [rbp+57h+lpAddress]; lpAddress
0x1800239fe  call    cs:__imp_VirtualProtect
0x180023a05  nop     dword ptr [rax+rax+00h]
0x180023a0a  cmp     [rbp+57h+var_38], 0
0x180023a0e  mov     [rbp+57h+flOldProtect], r14d
0x180023a12  jz      short loc_180023A43
0x180023a14  mov     [rbp+57h+var_7C], r14d
0x180023a18  call    cs:__imp_GetCurrentThread
0x180023a1f  nop     dword ptr [rax+rax+00h]
0x180023a24  mov     r9d, 4
0x180023a2a  lea     r8, [rbp+57h+var_7C]
0x180023a2e  mov     rcx, rax
0x180023a31  mov     edx, 2
0x180023a36  mov     rax, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x180023a3d  call    cs:__guard_dispatch_icall_fptr
0x180023a43  mov     eax, r15d
0x180023a46  mov     rcx, [rbp+57h+var_30]
0x180023a4a  xor     rcx, rsp; StackCookie
0x180023a4d  call    __security_check_cookie
0x180023a52  add     rsp, 0A0h
0x180023a59  pop     r15
0x180023a5b  pop     r14
0x180023a5d  pop     r13
0x180023a5f  pop     rsi
0x180023a60  pop     rbp
0x180023a61  retn
```
