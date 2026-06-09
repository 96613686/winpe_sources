# TpmApiCreateContext

- ea: `0x18007455c`
- end: `0x180074863`
- name: `TpmApiCreateContext`
- size: `775`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800549c0`

## callees

- `0x18007455c`
- `0x18007486c`
- `0x180074a1c`
- `0x180074a48`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18007461c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18007461c`
- `tbs!Tbsi_Context_Create` at `0x180074702`
- `tbs!Tbsi_Context_Create` at `0x180074702`

## pseudocode

```c
__int64 __fastcall TpmApiCreateContext(_DWORD *a1, __int64 *a2)
{
  signed int v4; // ebx
  __int64 v5; // r8
  _DWORD *v6; // rsi
  _DWORD *v7; // r14
  unsigned int v8; // ecx
  int v9; // eax
  PVOID phContext; // [rsp+28h] [rbp-20h] BYREF
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF
  __int64 pContextParams; // [rsp+68h] [rbp+20h] BYREF

  phContext = 0;
  pContextParams = 0;
  v12 = 0;
  g_fpGetMemory = (void *(*)(unsigned __int64))TpmApiPlatformGetMemory;
  g_fpFreeMemory = (void (*)(void *))TpmApiPlatformFreeMemory;
  g_fpTpmSubmit = (unsigned int (*)(unsigned __int8 *const, unsigned int, unsigned __int8 *, unsigned int *))TpmApiPlatformTbsSubmit;
  g_fpW8TpmSubmit = (unsigned int (*)(void *, unsigned __int8 *const, unsigned int, unsigned __int8 *, unsigned int *))TpmApiPlatformW8TbsSubmit;
  g_fpGetRandom = (int (*)(unsigned __int8 *, unsigned int))TpmApiPlatformGetRandom;
  g_fpSha1Hash = (int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int))TpmApiPlatformSha1Hash;
  g_fpHash = (int (*)(unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *, unsigned int))TpmApiPlatformHash;
  g_fpAesCfbEncrypt = (int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *))WinPlatformAesCfbEncrypt;
  g_fpAesCfbDecrypt = (int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *))WinPlatformAesCfbDecrypt;
  InitOnceExecuteOnce(&g_CallbackInitOnce, CheckAndInitCallbacksOnce, 0, 0);
  if ( a1 )
  {
    if ( a2 )
    {
      *a2 = 0;
      if ( *a1 == 12 && (v6 = a1 + 1, a1[1] == 1) && (v7 = a1 + 2, v8 = a1[2], v8 < 0x80000000) )
      {
        v9 = 1;
      }
      else
      {
        if ( *a1 != 16 || (v6 = a1 + 1, a1[1] != 2) || (v7 = a1 + 2, v8 = a1[2], v8 >= 0x80000000) )
        {
          v4 = -2144796395;
          v5 = v12;
          goto LABEL_38;
        }
        v9 = 2;
      }
      if ( v9 == 2 )
      {
        LODWORD(pContextParams) = 2;
        HIDWORD(pContextParams) = a1[3] | 4;
      }
      else if ( dword_1800C1970 == 2 )
      {
        pContextParams = 0x400000002LL;
        v7 = a1 + 2;
        v6 = a1 + 1;
      }
      else
      {
        LODWORD(pContextParams) = 1;
      }
      if ( v8 && (v4 = Tbsi_Context_Create((PCTBS_CONTEXT_PARAMS)&pContextParams, &phContext), v4 < 0) )
      {
        v5 = v12;
      }
      else
      {
        v4 = TpmApiCallbackAlloc(0, 32, &v12);
        if ( v4 >= 0 )
        {
          *(_DWORD *)v12 = 541278548;
          *(_DWORD *)(v12 + 4) = 24;
          *(_DWORD *)(v12 + 8) = 0;
          *(_DWORD *)(v12 + 12) = *v7;
          *(_QWORD *)(v12 + 16) = phContext;
          if ( *v6 == 2 || dword_1800C1970 == 2 )
          {
            *(_DWORD *)(v12 + 4) = 32;
            *(_DWORD *)(v12 + 24) = HIDWORD(pContextParams);
          }
          v5 = v12;
          if ( v12 )
          {
            if ( *(_DWORD *)v12 == 541278548 )
            {
              if ( ((*(_DWORD *)(v12 + 4) - 24) & 0xFFFFFFF7) != 0 )
              {
                v4 = -2144796395;
              }
              else if ( *(_DWORD *)(v12 + 8) )
              {
                v4 = -2144796395;
              }
              else if ( *(_DWORD *)(v12 + 12) < 0x80000000 )
              {
                *a2 = v12 ^ 0x1D9C0E3A;
                v5 = 0;
                v12 = 0;
              }
              else
              {
                v4 = -2144796395;
              }
            }
            else
            {
              v4 = -2144796395;
            }
          }
          else
          {
            v4 = -2144796412;
          }
        }
        else
        {
          v5 = v12;
        }
      }
    }
    else
    {
      v4 = -2144796413;
      v5 = v12;
    }
  }
  else
  {
    v4 = -2144796412;
    v5 = v12;
  }
LABEL_38:
  TpmApiCallbackFree(0, 24, v5);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18007455c  mov     rax, rsp
0x18007455f  mov     [rax+8], rbx
0x180074563  push    rsi
0x180074564  push    r14
0x180074566  push    r15
0x180074568  sub     rsp, 30h
0x18007456c  mov     r15, rdx
0x18007456f  mov     rbx, rcx
0x180074572  mov     qword ptr [rax-20h], 0
0x18007457a  mov     qword ptr [rax+20h], 0
0x180074582  mov     qword ptr [rax+18h], 0
0x18007458a  lea     rax, ?TpmApiPlatformGetMemory@@YAPEAX_K@Z; TpmApiPlatformGetMemory(unsigned __int64)
0x180074591  mov     cs:?g_fpGetMemory@@3P6APEAX_K@ZEA, rax; void * (*g_fpGetMemory)(unsigned __int64)
0x180074598  lea     rax, ?TpmApiPlatformFreeMemory@@YAXPEAX@Z; TpmApiPlatformFreeMemory(void *)
0x18007459f  mov     cs:?g_fpFreeMemory@@3P6AXPEAX@ZEA, rax; void (*g_fpFreeMemory)(void *)
0x1800745a6  lea     rax, ?TpmApiPlatformTbsSubmit@@YAIQEAEIPEAEPEAI@Z; TpmApiPlatformTbsSubmit(uchar * const,uint,uchar *,uint *)
0x1800745ad  mov     cs:?g_fpTpmSubmit@@3P6AIQEAEIPEAEPEAI@ZEA, rax; uint (*g_fpTpmSubmit)(uchar * const,uint,uchar *,uint *)
0x1800745b4  lea     rax, ?TpmApiPlatformW8TbsSubmit@@YAIPEAXQEAEIPEAEPEAI@Z; TpmApiPlatformW8TbsSubmit(void *,uchar * const,uint,uchar *,uint *)
0x1800745bb  mov     cs:?g_fpW8TpmSubmit@@3P6AIPEAXQEAEIPEAEPEAI@ZEA, rax; uint (*g_fpW8TpmSubmit)(void *,uchar * const,uint,uchar *,uint *)
0x1800745c2  lea     rax, ?TpmApiPlatformGetRandom@@YAJPEAEI@Z; TpmApiPlatformGetRandom(uchar *,uint)
0x1800745c9  mov     cs:?g_fpGetRandom@@3P6AJPEAEI@ZEA, rax; long (*g_fpGetRandom)(uchar *,uint)
0x1800745d0  lea     rax, ?TpmApiPlatformSha1Hash@@YAJPEAEI0I0I@Z; TpmApiPlatformSha1Hash(uchar *,uint,uchar *,uint,uchar *,uint)
0x1800745d7  mov     cs:?g_fpSha1Hash@@3P6AJPEAEI0I0I@ZEA, rax; long (*g_fpSha1Hash)(uchar *,uint,uchar *,uint,uchar *,uint)
0x1800745de  lea     rax, ?TpmApiPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z; TpmApiPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x1800745e5  mov     cs:?g_fpHash@@3P6AJPEAGPEAEI1I1IPEAIK@ZEA, rax; long (*g_fpHash)(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x1800745ec  lea     rax, ?WinPlatformAesCfbEncrypt@@YAJPEAEI0I0I0@Z; WinPlatformAesCfbEncrypt(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x1800745f3  mov     cs:?g_fpAesCfbEncrypt@@3P6AJPEAEI0I0I0@ZEA, rax; long (*g_fpAesCfbEncrypt)(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x1800745fa  lea     rax, ?WinPlatformAesCfbDecrypt@@YAJPEAEI0I0I0@Z; WinPlatformAesCfbDecrypt(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x180074601  mov     cs:?g_fpAesCfbDecrypt@@3P6AJPEAEI0I0I0@ZEA, rax; long (*g_fpAesCfbDecrypt)(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x180074608  xor     r9d, r9d; Context
0x18007460b  xor     r8d, r8d; Parameter
0x18007460e  lea     rdx, ?CheckAndInitCallbacksOnce@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180074615  lea     rcx, ?g_CallbackInitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18007461c  call    cs:__imp_InitOnceExecuteOnce
0x180074623  nop     dword ptr [rax+rax+00h]
0x180074628  test    rbx, rbx
0x18007462b  jnz     short loc_180074640
0x18007462d  mov     ebx, 80290104h
0x180074632  mov     [rsp+48h+var_28], ebx
0x180074636  mov     r8, [rsp+48h+arg_10]
0x18007463b  jmp     loc_180074845
0x180074640  test    r15, r15
0x180074643  jnz     short loc_180074658
0x180074645  mov     ebx, 80290103h
0x18007464a  mov     [rsp+48h+var_28], ebx
0x18007464e  mov     r8, [rsp+48h+arg_10]
0x180074653  jmp     loc_180074845
0x180074658  xor     eax, eax
0x18007465a  mov     [r15], rax
0x18007465d  cmp     dword ptr [rbx], 0Ch
0x180074660  jnz     short loc_180074681
0x180074662  lea     rsi, [rbx+4]
0x180074666  cmp     dword ptr [rsi], 1
0x180074669  jnz     short loc_180074681
0x18007466b  lea     r14, [rbx+8]
0x18007466f  mov     ecx, [r14]
0x180074672  cmp     ecx, 80000000h
0x180074678  jnb     short loc_180074681
0x18007467a  mov     eax, 1
0x18007467f  jmp     short loc_1800746AF
0x180074681  cmp     dword ptr [rbx], 10h
0x180074684  jnz     loc_180074826
0x18007468a  lea     rsi, [rbx+4]
0x18007468e  cmp     dword ptr [rsi], 2
0x180074691  jnz     loc_180074826
0x180074697  lea     r14, [rbx+8]
0x18007469b  mov     ecx, [r14]
0x18007469e  cmp     ecx, 80000000h
0x1800746a4  jnb     loc_180074826
0x1800746aa  mov     eax, 2
0x1800746af  cmp     eax, 2
0x1800746b2  jnz     short loc_1800746C8
0x1800746b4  mov     dword ptr [rsp+48h+pContextParams], eax
0x1800746b8  mov     eax, [rbx+0Ch]
0x1800746bb  mov     dword ptr [rsp+48h+pContextParams+4], eax
0x1800746bf  or      eax, 4
0x1800746c2  mov     dword ptr [rsp+48h+pContextParams+4], eax
0x1800746c6  jmp     short loc_1800746F4
0x1800746c8  cmp     cs:dword_1800C1970, 2
0x1800746cf  jnz     short loc_1800746EC
0x1800746d1  mov     [rsp+48h+pContextParams], 2
0x1800746da  mov     dword ptr [rsp+48h+pContextParams+4], 4
0x1800746e2  lea     r14, [rbx+8]
0x1800746e6  lea     rsi, [rbx+4]
0x1800746ea  jmp     short loc_1800746F4
0x1800746ec  mov     dword ptr [rsp+48h+pContextParams], 1
0x1800746f4  test    ecx, ecx
0x1800746f6  jz      short loc_180074722
0x1800746f8  lea     rdx, [rsp+48h+phContext]; phContext
0x1800746fd  lea     rcx, [rsp+48h+pContextParams]; pContextParams
0x180074702  call    cs:__imp_Tbsi_Context_Create
0x180074709  nop     dword ptr [rax+rax+00h]
0x18007470e  mov     ebx, eax
0x180074710  mov     [rsp+48h+var_28], eax
0x180074714  test    eax, eax
0x180074716  jns     short loc_180074722
0x180074718  mov     r8, [rsp+48h+arg_10]
0x18007471d  jmp     loc_180074845
0x180074722  lea     r8, [rsp+48h+arg_10]
0x180074727  mov     edx, 20h ; ' '
0x18007472c  xor     ecx, ecx
0x18007472e  call    TpmApiCallbackAlloc
0x180074733  mov     ebx, eax
0x180074735  mov     [rsp+48h+var_28], eax
0x180074739  test    eax, eax
0x18007473b  jns     short loc_180074747
0x18007473d  mov     r8, [rsp+48h+arg_10]
0x180074742  jmp     loc_180074845
0x180074747  mov     edx, 20434154h
0x18007474c  mov     rax, [rsp+48h+arg_10]
0x180074751  mov     [rax], edx
0x180074753  mov     rax, [rsp+48h+arg_10]
0x180074758  mov     dword ptr [rax+4], 18h
0x18007475f  mov     rax, [rsp+48h+arg_10]
0x180074764  mov     dword ptr [rax+8], 0
0x18007476b  mov     ecx, [r14]
0x18007476e  mov     rax, [rsp+48h+arg_10]
0x180074773  mov     [rax+0Ch], ecx
0x180074776  mov     rcx, [rsp+48h+phContext]
0x18007477b  mov     rax, [rsp+48h+arg_10]
0x180074780  mov     [rax+10h], rcx
0x180074784  cmp     dword ptr [rsi], 2
0x180074787  jz      short loc_180074792
0x180074789  cmp     cs:dword_1800C1970, 2
0x180074790  jnz     short loc_1800747AA
0x180074792  mov     rax, [rsp+48h+arg_10]
0x180074797  mov     dword ptr [rax+4], 20h ; ' '
0x18007479e  mov     rax, [rsp+48h+arg_10]
0x1800747a3  mov     ecx, dword ptr [rsp+48h+pContextParams+4]
0x1800747a7  mov     [rax+18h], ecx
0x1800747aa  mov     r8, [rsp+48h+arg_10]
0x1800747af  test    r8, r8
0x1800747b2  jnz     short loc_1800747C2
0x1800747b4  mov     ebx, 80290104h
0x1800747b9  mov     [rsp+48h+var_28], ebx
0x1800747bd  jmp     loc_180074845
0x1800747c2  cmp     [r8], edx
0x1800747c5  jz      short loc_1800747D2
0x1800747c7  mov     ebx, 80290115h
0x1800747cc  mov     [rsp+48h+var_28], ebx
0x1800747d0  jmp     short loc_180074845
0x1800747d2  mov     eax, [r8+4]
0x1800747d6  sub     eax, 18h
0x1800747d9  test    eax, 0FFFFFFF7h
0x1800747de  jz      short loc_1800747EB
0x1800747e0  mov     ebx, 80290115h
0x1800747e5  mov     [rsp+48h+var_28], ebx
0x1800747e9  jmp     short loc_180074845
0x1800747eb  cmp     dword ptr [r8+8], 0
0x1800747f0  jz      short loc_1800747FD
0x1800747f2  mov     ebx, 80290115h
0x1800747f7  mov     [rsp+48h+var_28], ebx
0x1800747fb  jmp     short loc_180074845
0x1800747fd  cmp     dword ptr [r8+0Ch], 80000000h
0x180074805  jb      short loc_180074812
0x180074807  mov     ebx, 80290115h
0x18007480c  mov     [rsp+48h+var_28], ebx
0x180074810  jmp     short loc_180074845
0x180074812  xor     r8, 1D9C0E3Ah
0x180074819  mov     [r15], r8
0x18007481c  xor     r8d, r8d
0x18007481f  mov     [rsp+48h+arg_10], r8
0x180074824  jmp     short loc_180074845
0x180074826  mov     ebx, 80290115h
0x18007482b  mov     [rsp+48h+var_28], ebx
0x18007482f  mov     r8, [rsp+48h+arg_10]
0x180074834  jmp     short loc_180074845
0x180074836  mov     ebx, eax
0x180074838  bts     ebx, 1Ch
0x18007483c  mov     [rsp+48h+var_28], ebx
0x180074840  mov     r8, [rsp+48h+arg_10]
0x180074845  mov     edx, 18h
0x18007484a  xor     ecx, ecx
0x18007484c  call    TpmApiCallbackFree
0x180074851  mov     eax, ebx
0x180074853  mov     rbx, [rsp+48h+arg_0]
0x180074858  add     rsp, 30h
0x18007485c  pop     r15
0x18007485e  pop     r14
0x180074860  pop     rsi
0x180074861  retn
0x18007fb21  push    rbp
0x18007fb23  sub     rsp, 20h
0x18007fb27  mov     rbp, rdx
0x18007fb2a  mov     rax, [rcx]
0x18007fb2d  cmp     dword ptr [rax], 0C0000005h
0x18007fb33  jz      short loc_18007FB49
0x18007fb35  cmp     dword ptr [rax], 80000002h
0x18007fb3b  jz      short loc_18007FB49
0x18007fb3d  cmp     dword ptr [rax], 0C0000008h
0x18007fb43  jz      short loc_18007FB49
0x18007fb45  xor     eax, eax
0x18007fb47  jmp     short loc_18007FB4E
0x18007fb49  mov     eax, 1
0x18007fb4e  add     rsp, 20h
0x18007fb52  pop     rbp
0x18007fb53  retn
```
