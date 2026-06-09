# BCryptDestroyHash

- ea: `0x180006da0`
- end: `0x1800070c8`
- name: `BCryptDestroyHash`
- size: `808`
- prototype: `NTSTATUS __stdcall(BCRYPT_HASH_HANDLE hHash)`
- caller_count: `8`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005470`
- `0x18000c1e0`
- `0x18000cb70`
- `0x180012cc4`
- `0x180016564`
- `0x1800168c8`
- `0x180016efc`
- `0x1800171b4`

## callees

- `0x180005060`
- `0x180006da0`
- `0x180007a7c`
- `0x180009430`
- `0x18000cd9c`
- `0x18000d948`
- `0x18001aa70`
- `0x18001aa9c`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180006e44`
- `ntdll!RtlFreeHeap` at `0x180006f1f`
- `ntdll!RtlFreeHeap` at `0x180006e44`
- `ntdll!RtlFreeHeap` at `0x180006f1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006edf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006edf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006ea7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006ea7`

## string_xrefs

- `0x180006f59`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180006fb0`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000700f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000704e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180007071`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptDestroyHash(BCRYPT_HASH_HANDLE hHash)
{
  int v1; // edx
  __int64 v2; // r8
  _QWORD *v4; // rcx
  unsigned int *v5; // rbp
  void *v6; // rdi
  int v7; // edx
  int v8; // esi
  int v9; // r8d
  __int64 v10; // rax
  unsigned int v11; // eax
  int v12; // eax
  __int64 v13; // rbx
  int v14; // edx
  int v15; // r8d
  __int64 v16; // rcx
  _BYTE *v17; // rax
  int v19; // eax
  __int64 v20; // rcx
  void *v21; // rcx

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, v2);
    v4 = WPP_GLOBAL_Control;
  }
  if ( hHash && *(_DWORD *)hHash >= 0x28u && *((_DWORD *)hHash + 1) == 1431655763 )
  {
    v5 = (unsigned int *)*((_QWORD *)hHash + 1);
    v6 = (void *)*((_QWORD *)hHash + 4);
    v8 = (*((__int64 (__fastcall **)(_QWORD))v5 + 15))(*((_QWORD *)hHash + 2));
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v7,
          v9,
          (unsigned int)"Status",
          v8,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
          5);
    }
    else if ( (v5[2] & 8) != 0
           && (v19 = (*((__int64 (__fastcall **)(_QWORD))v5 + 15))(*((_QWORD *)hHash + 3)), v8 = v19, v19 < 0) )
    {
      DebugTraceError((unsigned int)v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 6416);
    }
    else
    {
      v10 = *(unsigned int *)hHash;
      if ( *(_DWORD *)hHash )
      {
        do
        {
          *(_BYTE *)hHash = 0;
          hHash = (char *)hHash + 1;
          --v10;
        }
        while ( v10 );
      }
      if ( v6 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
      v8 = 0;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 4, 0xFFFFFFFF) == 1 )
      {
        v11 = v5[9];
        if ( v11 == 1 )
        {
LABEL_13:
          v12 = (*((__int64 (__fastcall **)(_QWORD, _QWORD))v5 + 10))(*((_QWORD *)v5 + 3), 0);
          if ( v12 < 0 )
          {
            DebugTraceError((unsigned int)v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 960);
          }
          else
          {
            if ( g_fLoaderInitialized )
            {
              v13 = *((_QWORD *)v5 + 5);
              if ( v13 )
              {
                EnterCriticalSection(&g_csLoaderLock);
                --*(_DWORD *)(v13 + 16);
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
                {
                  WPP_SF_qSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, v13, *(_QWORD *)v13, *(_DWORD *)(v13 + 16));
                }
                if ( !*(_DWORD *)(v13 + 16) )
                {
                  v20 = *(_QWORD *)(v13 + 8);
                  if ( v20 )
                    FreeImage(v20);
                  RemoveFromLoadedProviderList(v13);
                  MSCryptFree(v21);
                }
                LeaveCriticalSection(&g_csLoaderLock);
              }
            }
            v16 = *v5;
            v17 = v5;
            if ( *v5 )
            {
              do
              {
                *v17++ = 0;
                --v16;
              }
              while ( v16 );
            }
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
          }
        }
        else
        {
          switch ( v11 )
          {
            case 2u:
            case 3u:
            case 4u:
            case 5u:
            case 6u:
            case 7u:
            case 8u:
              goto LABEL_13;
            default:
              DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 951);
              break;
          }
        }
      }
    }
  }
  else
  {
    v8 = -1073741811;
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        v4[2],
        v1,
        v2,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        248);
  }
  return v8;
}

```

## disassembly

```asm
0x180006da0  push    rbx
0x180006da2  push    rsi
0x180006da3  push    r14
0x180006da5  sub     rsp, 40h
0x180006da9  mov     rbx, rcx
0x180006dac  mov     rcx, cs:WPP_GLOBAL_Control
0x180006db3  lea     r14, WPP_GLOBAL_Control
0x180006dba  cmp     rcx, r14
0x180006dbd  jnz     loc_180006F6F
0x180006dc3  mov     [rsp+58h+arg_8], rbp
0x180006dc8  mov     [rsp+58h+arg_10], rdi
0x180006dcd  test    rbx, rbx
0x180006dd0  jz      loc_180006F41
0x180006dd6  cmp     dword ptr [rbx], 28h ; '('
0x180006dd9  jb      loc_180006F41
0x180006ddf  cmp     dword ptr [rbx+4], 55555553h
0x180006de6  jnz     loc_180006F41
0x180006dec  mov     rbp, [rbx+8]
0x180006df0  mov     rcx, [rbx+10h]
0x180006df4  mov     rdi, [rbx+20h]
0x180006df8  mov     rax, [rbp+78h]
0x180006dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e01  mov     esi, eax
0x180006e03  test    eax, eax
0x180006e05  js      loc_180006F96
0x180006e0b  test    byte ptr [rbp+8], 8
0x180006e0f  jnz     loc_180006FF2
0x180006e15  mov     eax, [rbx]
0x180006e17  test    rax, rax
0x180006e1a  jz      short loc_180006E2D
0x180006e1c  nop     dword ptr [rax+00h]
0x180006e20  mov     byte ptr [rbx], 0
0x180006e23  lea     rbx, [rbx+1]
0x180006e27  sub     rax, 1
0x180006e2b  jnz     short loc_180006E20
0x180006e2d  test    rdi, rdi
0x180006e30  jz      short loc_180006E50
0x180006e32  mov     rcx, gs:60h
0x180006e3b  mov     r8, rdi; P
0x180006e3e  xor     edx, edx; Flags
0x180006e40  mov     rcx, [rcx+30h]; HeapHandle
0x180006e44  call    cs:__imp_RtlFreeHeap
0x180006e4b  nop     dword ptr [rax+rax+00h]
0x180006e50  mov     eax, 0FFFFFFFFh
0x180006e55  lock xadd [rbp+10h], eax
0x180006e5a  mov     esi, 0
0x180006e5f  cmp     eax, 1
0x180006e62  jnz     loc_180006F2B
0x180006e68  mov     eax, [rbp+24h]
0x180006e6b  cmp     eax, 1
0x180006e6e  jnz     loc_180007029
0x180006e74  mov     rcx, [rbp+18h]; jumptable 0000000180007042 cases 2-8
0x180006e78  xor     edx, edx
0x180006e7a  mov     rax, [rbp+50h]
0x180006e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e83  mov     ecx, eax
0x180006e85  test    eax, eax
0x180006e87  js      loc_18000706B
0x180006e8d  xor     edi, edi
0x180006e8f  cmp     cs:g_fLoaderInitialized, esi
0x180006e95  jz      short loc_180006EEB
0x180006e97  mov     rbx, [rbp+28h]
0x180006e9b  test    rbx, rbx
0x180006e9e  jz      short loc_180006EEB
0x180006ea0  lea     rcx, g_csLoaderLock; lpCriticalSection
0x180006ea7  call    cs:__imp_EnterCriticalSection
0x180006eae  nop     dword ptr [rax+rax+00h]
0x180006eb3  dec     dword ptr [rbx+10h]
0x180006eb6  mov     eax, [rbx+10h]
0x180006eb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ec0  cmp     rcx, r14
0x180006ec3  jz      short loc_180006ECF
0x180006ec5  test    byte ptr [rcx+1Ch], 20h
0x180006ec9  jnz     loc_180006FD5
0x180006ecf  cmp     [rbx+10h], esi
0x180006ed2  jz      loc_180007089
0x180006ed8  lea     rcx, g_csLoaderLock; lpCriticalSection
0x180006edf  call    cs:__imp_LeaveCriticalSection
0x180006ee6  nop     dword ptr [rax+rax+00h]
0x180006eeb  mov     ecx, [rbp+0]
0x180006eee  mov     rax, rbp
0x180006ef1  test    rcx, rcx
0x180006ef4  jz      short loc_180006F0D
0x180006ef6  nop     word ptr [rax+rax+00000000h]
0x180006f00  mov     [rax], sil
0x180006f03  lea     rax, [rax+1]
0x180006f07  sub     rcx, 1
0x180006f0b  jnz     short loc_180006F00
0x180006f0d  mov     rcx, gs:60h
0x180006f16  mov     r8, rbp; P
0x180006f19  xor     edx, edx; Flags
0x180006f1b  mov     rcx, [rcx+30h]; HeapHandle
0x180006f1f  call    cs:__imp_RtlFreeHeap
0x180006f26  nop     dword ptr [rax+rax+00h]
0x180006f2b  mov     rdi, [rsp+58h+arg_10]
0x180006f30  mov     eax, esi
0x180006f32  mov     rbp, [rsp+58h+arg_8]
0x180006f37  add     rsp, 40h
0x180006f3b  pop     r14
0x180006f3d  pop     rsi
0x180006f3e  pop     rbx
0x180006f3f  retn
0x180006f41  mov     esi, 0C000000Dh
0x180006f46  cmp     rcx, r14
0x180006f49  jz      short loc_180006F2B
0x180006f4b  test    byte ptr [rcx+1Ch], 1
0x180006f4f  jz      short loc_180006F2B
0x180006f51  mov     [rsp+58h+var_28], 18F8h
0x180006f59  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006f60  mov     [rsp+58h+var_30], rax
0x180006f65  mov     dword ptr [rsp+58h+var_38], 0C000000Dh
0x180006f6d  jmp     short loc_180006FC0
0x180006f6f  test    byte ptr [rcx+1Ch], 4
0x180006f73  jz      loc_180006DC3
0x180006f79  mov     rcx, [rcx+10h]
0x180006f7d  mov     edx, 24h ; '$'
0x180006f82  mov     r9, rbx
0x180006f85  call    WPP_SF_q
0x180006f8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f91  jmp     loc_180006DC3
0x180006f96  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f9d  cmp     rcx, r14
0x180006fa0  jz      short loc_180006F2B
0x180006fa2  test    byte ptr [rcx+1Ch], 1
0x180006fa6  jz      short loc_180006F2B
0x180006fa8  mov     [rsp+58h+var_28], 1905h
0x180006fb0  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006fb7  mov     [rsp+58h+var_30], rax
0x180006fbc  mov     dword ptr [rsp+58h+var_38], esi
0x180006fc0  mov     rcx, [rcx+10h]
0x180006fc4  lea     r9, aStatus; "Status"
0x180006fcb  call    WPP_SF_sDsd
0x180006fd0  jmp     loc_180006F2B
0x180006fd5  mov     rcx, [rcx+10h]
0x180006fd9  mov     r9, rbx
0x180006fdc  mov     dword ptr [rsp+58h+var_30], eax
0x180006fe0  mov     rax, [rbx]
0x180006fe3  mov     [rsp+58h+var_38], rax
0x180006fe8  call    WPP_SF_qSD
0x180006fed  jmp     loc_180006ECF
0x180006ff2  mov     rcx, [rbx+18h]
0x180006ff6  mov     rax, [rbp+78h]
0x180006ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fff  mov     esi, eax
0x180007001  test    eax, eax
0x180007003  jns     loc_180006E15
0x180007009  mov     r9d, 1910h
0x18000700f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007016  lea     rdx, aStatus; "Status"
0x18000701d  mov     ecx, eax
0x18000701f  call    DebugTraceError
0x180007024  jmp     loc_180006F2B
0x180007029  add     eax, 0FFFFFFFEh; switch 7 cases
0x18000702c  cmp     eax, 6
0x18000702f  ja      short def_180007042; jumptable 0000000180007042 default case
0x180007031  lea     rcx, __ImageBase
0x180007038  mov     eax, ds:(jpt_180007042 - 180000000h)[rcx+rax*4]
0x18000703f  add     rax, rcx
0x180007042  jmp     rax; switch jump
0x180007048  mov     r9d, 3B7h; jumptable 0000000180007042 default case
0x18000704e  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007055  lea     rdx, aStatus; "Status"
0x18000705c  mov     ecx, 0C0000008h
0x180007061  call    DebugTraceError
0x180007066  jmp     loc_180006F2B
0x18000706b  mov     r9d, 3C0h
0x180007071  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007078  lea     rdx, aStatus; "Status"
0x18000707f  call    DebugTraceError
0x180007084  jmp     loc_180006F2B
0x180007089  mov     rcx, [rbx+8]
0x18000708d  test    rcx, rcx
0x180007090  jz      short loc_180007097
0x180007092  call    _FreeImage
0x180007097  mov     rcx, rbx
0x18000709a  call    _RemoveFromLoadedProviderList
0x18000709f  call    MSCryptFree
0x1800070a4  jmp     loc_180006ED8
```
