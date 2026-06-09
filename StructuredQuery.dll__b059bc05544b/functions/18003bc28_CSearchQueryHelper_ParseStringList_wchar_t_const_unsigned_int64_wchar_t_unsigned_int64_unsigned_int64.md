# CSearchQueryHelper::_ParseStringList(wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64,unsigned __int64 *)

- ea: `0x18003bc28`
- end: `0x18003bebd`
- name: `?_ParseStringList@CSearchQueryHelper@@AEAAJPEB_W_KPEAPEA_W1PEA_K@Z`
- size: `661`
- prototype: `__int64 __fastcall(WORD *this, const wchar_t *, __int64, wchar_t **, unsigned __int64, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003ba88`
- `0x180072eb0`

## callees

- `0x18001ee60`
- `0x180020250`
- `0x18003bc28`
- `0x180059920`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!GetStringTypeExW` at `0x18003bcc5`
- `api-ms-win-core-string-l1-1-0!GetStringTypeExW` at `0x18003bcc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003be6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003be8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003be6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003be8b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSearchQueryHelper::_ParseStringList(
        WORD *this,
        const wchar_t *a2,
        __int64 a3,
        wchar_t **a4,
        unsigned __int64 a5,
        unsigned __int64 *a6)
{
  const size_t *v6; // rbp
  const wchar_t *v8; // r14
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rdi
  unsigned __int64 v11; // rcx
  int Error; // ebx
  LPWORD v13; // r12
  WORD *v14; // r8
  WORD *v15; // r9
  int v16; // edx
  WORD *v17; // r13
  int *v18; // rcx
  int v19; // esi
  __int64 v20; // rcx
  int v21; // r11d
  const size_t *v22; // r9
  int v23; // r8d
  unsigned __int64 i; // rax
  __int64 v25; // rdx
  int lpCharType; // [rsp+20h] [rbp-58h]
  WORD *v28; // [rsp+30h] [rbp-48h]
  LPWORD v29; // [rsp+80h] [rbp+8h] BYREF
  __int64 v30; // [rsp+90h] [rbp+18h]

  v30 = a3;
  v29 = this;
  v6 = 0;
  v8 = a2;
  v9 = -1;
  v10 = 0;
  do
    ++v9;
  while ( a2[v9] );
  v11 = v9 + 1;
  if ( v9 + 1 >= v9 && (v29 = 0, is_mul_ok(v11, 2u)) )
  {
    Error = CTCoAllocPolicy::Alloc((void *)v11, 1u, 2 * v11, (void **)&v29);
    if ( Error >= 0 )
    {
      v13 = v29;
      if ( GetStringTypeExW(0x7Fu, 1u, v8, -1, v29) )
      {
        v14 = (WORD *)&v8[v9];
        Error = 0;
        v15 = &v13[v9];
        v29 = v14;
        v28 = v15;
        v16 = 2;
        v17 = v13;
        while ( 1 )
        {
          if ( v16 == 3 )
            goto LABEL_57;
          if ( *v8 )
          {
            if ( (*(_BYTE *)v17 & 0x68) != 0 )
            {
              v18 = &dword_1800A14E4;
            }
            else
            {
              v18 = (int *)byte_1800A14E8;
              if ( *v8 != 44 )
                v18 = &dword_1800A14EC;
            }
          }
          else
          {
            v18 = (int *)&rgrgStateTokenMap;
          }
          v19 = v18[4 * v16];
          if ( v16 )
          {
            if ( !v19 )
              v6 = (const size_t *)v8;
            goto LABEL_42;
          }
          if ( !v19 )
            goto LABEL_42;
          v20 = ((char *)v8 - (char *)v6) >> 1;
          if ( (int)v20 <= 0 )
            goto LABEL_42;
          if ( a4 )
            break;
LABEL_39:
          if ( Error >= 0 && ++v10 == v30 )
            v19 = 3;
LABEL_42:
          if ( v8 < v14 )
            ++v8;
          if ( v17 < v15 )
            ++v17;
          if ( v19 == 4 )
          {
            Error = -2147024809;
LABEL_51:
            if ( a4 )
            {
              while ( v10 )
              {
                CoTaskMemFree(a4[--v10]);
                a4[v10] = 0;
              }
            }
            else
            {
              v10 = 0;
            }
            goto LABEL_57;
          }
          if ( Error < 0 )
            goto LABEL_51;
          v16 = v19;
        }
        if ( v10 >= a5 )
        {
          Error = -2147024809;
          goto LABEL_42;
        }
        if ( *(_WORD *)v6 == 34 )
        {
          v6 = (const size_t *)((char *)v6 + 2);
          v21 = 1;
          v20 = (unsigned int)(v20 - 1);
          v22 = v6;
          if ( (int)v20 <= 0 )
            goto LABEL_24;
        }
        else
        {
          v21 = 0;
          v22 = v6;
        }
        if ( *((_WORD *)v6 + (int)v20 - 1) == 34 )
        {
          v20 = (unsigned int)(v20 - 1);
          v23 = 1;
LABEL_25:
          for ( i = 0; ; ++i )
          {
            v25 = 0;
            if ( i >= (int)v20 )
              break;
            if ( *((_WORD *)v22 + i) == 34 )
            {
              v25 = 1;
              break;
            }
          }
          if ( v21 != v23 || (int)v20 <= 0 || (_DWORD)v25 )
            Error = -2147024809;
          else
            Error = _AllocStringWorker<CTCoAllocPolicy>(v20, v25, v6, (int)v20, lpCharType, &a4[v10]);
          v14 = v29;
          v15 = v28;
          goto LABEL_39;
        }
LABEL_24:
        v23 = 0;
        goto LABEL_25;
      }
      Error = ResultFromKnownLastError();
LABEL_57:
      CoTaskMemFree(v13);
    }
  }
  else
  {
    Error = -2147024362;
  }
  *a6 = v10;
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18003bc28  mov     [rsp+arg_8], rbx
0x18003bc2d  mov     [rsp+arg_10], r8
0x18003bc32  mov     [rsp+arg_0], rcx
0x18003bc37  push    rbp
0x18003bc38  push    rsi
0x18003bc39  push    rdi
0x18003bc3a  push    r12
0x18003bc3c  push    r13
0x18003bc3e  push    r14
0x18003bc40  push    r15
0x18003bc42  sub     rsp, 40h
0x18003bc46  xor     ebp, ebp
0x18003bc48  mov     r15, r9
0x18003bc4b  or      r13, 0FFFFFFFFFFFFFFFFh
0x18003bc4f  mov     r14, rdx
0x18003bc52  mov     rsi, r13
0x18003bc55  mov     edi, ebp
0x18003bc57  inc     rsi
0x18003bc5a  cmp     [rdx+rsi*2], bp
0x18003bc5e  jnz     short loc_18003BC57
0x18003bc60  lea     rcx, [rsi+1]; void *
0x18003bc64  cmp     rcx, rsi
0x18003bc67  jb      loc_18003BE93
0x18003bc6d  mov     eax, 2
0x18003bc72  mov     [rsp+78h+arg_0], rbp
0x18003bc7a  mul     rcx
0x18003bc7d  mov     [rsp+78h+var_48], rbp
0x18003bc82  test    rdx, rdx
0x18003bc85  jnz     loc_18003BE93
0x18003bc8b  lea     r9, [rsp+78h+arg_0]; void **
0x18003bc93  mov     r8, rax; unsigned __int64
0x18003bc96  mov     edx, 1; unsigned int
0x18003bc9b  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18003bca0  mov     ebx, eax
0x18003bca2  test    eax, eax
0x18003bca4  js      loc_18003BE98
0x18003bcaa  mov     r12, [rsp+78h+arg_0]
0x18003bcb2  mov     edx, 1; dwInfoType
0x18003bcb7  mov     r9d, r13d; cchSrc
0x18003bcba  mov     [rsp+78h+lpCharType], r12; lpCharType
0x18003bcbf  mov     r8, r14; lpSrcStr
0x18003bcc2  lea     ecx, [rdx+7Eh]; Locale
0x18003bcc5  call    cs:__imp_GetStringTypeExW
0x18003bccb  xor     r10d, r10d
0x18003bcce  test    eax, eax
0x18003bcd0  jz      loc_18003BE81
0x18003bcd6  lea     r8, [r14+rsi*2]
0x18003bcda  mov     ebx, r10d
0x18003bcdd  lea     r9, [r12+rsi*2]
0x18003bce1  mov     [rsp+78h+arg_0], r8
0x18003bce9  mov     [rsp+78h+var_48], r9
0x18003bcee  lea     edx, [r10+2]
0x18003bcf2  mov     r13, r12
0x18003bcf5  lea     r11d, [r10+3]
0x18003bcf9  cmp     edx, r11d
0x18003bcfc  jz      loc_18003BE88
0x18003bd02  cmp     [r14], r10w
0x18003bd06  jnz     short loc_18003BD11
0x18003bd08  lea     rcx, ?rgrgStateTokenMap@@3PAY03W4STRING_STATE@@A; STRING_STATE (near * rgrgStateTokenMap)[4]
0x18003bd0f  jmp     short loc_18003BD38
0x18003bd11  test    byte ptr [r13+0], 68h
0x18003bd16  jz      short loc_18003BD21
0x18003bd18  lea     rcx, dword_1800A14E4
0x18003bd1f  jmp     short loc_18003BD38
0x18003bd21  cmp     word ptr [r14], 2Ch ; ','
0x18003bd26  lea     rcx, byte_1800A14E8
0x18003bd2d  lea     rax, dword_1800A14EC
0x18003bd34  cmovnz  rcx, rax
0x18003bd38  movsxd  rax, edx
0x18003bd3b  add     rax, rax
0x18003bd3e  mov     esi, [rcx+rax*8]
0x18003bd41  test    edx, edx
0x18003bd43  jz      short loc_18003BD55
0x18003bd45  test    esi, esi
0x18003bd47  jnz     loc_18003BE2D
0x18003bd4d  mov     rbp, r14
0x18003bd50  jmp     loc_18003BE2D
0x18003bd55  test    esi, esi
0x18003bd57  jz      loc_18003BE2D
0x18003bd5d  mov     rcx, r14
0x18003bd60  sub     rcx, rbp
0x18003bd63  sar     rcx, 1
0x18003bd66  test    ecx, ecx
0x18003bd68  jle     loc_18003BE2D
0x18003bd6e  test    r15, r15
0x18003bd71  jz      loc_18003BE1A
0x18003bd77  cmp     rdi, [rsp+78h+arg_20]
0x18003bd7f  jnb     loc_18003BE4F
0x18003bd85  cmp     word ptr [rbp+0], 22h ; '"'
0x18003bd8a  jnz     short loc_18003BDBC
0x18003bd8c  add     rbp, 2
0x18003bd90  mov     r11d, 1
0x18003bd96  dec     ecx
0x18003bd98  mov     r9, rbp
0x18003bd9b  test    ecx, ecx
0x18003bd9d  jg      short loc_18003BDC2
0x18003bd9f  mov     r8d, r10d
0x18003bda2  mov     rax, r10
0x18003bda5  movsxd  r10, ecx
0x18003bda8  xor     edx, edx
0x18003bdaa  cmp     rax, r10
0x18003bdad  jnb     short loc_18003BDDC
0x18003bdaf  cmp     word ptr [r9+rax*2], 22h ; '"'
0x18003bdb5  jz      short loc_18003BDD7
0x18003bdb7  inc     rax
0x18003bdba  jmp     short loc_18003BDA8
0x18003bdbc  mov     r11d, r10d
0x18003bdbf  mov     r9, rbp
0x18003bdc2  movsxd  rax, ecx
0x18003bdc5  cmp     word ptr [rbp+rax*2-2], 22h ; '"'
0x18003bdcb  jnz     short loc_18003BD9F
0x18003bdcd  dec     ecx
0x18003bdcf  mov     r8d, 1
0x18003bdd5  jmp     short loc_18003BDA2
0x18003bdd7  mov     edx, 1
0x18003bddc  cmp     r11d, r8d
0x18003bddf  jnz     short loc_18003BE01
0x18003bde1  test    ecx, ecx
0x18003bde3  jle     short loc_18003BE01
0x18003bde5  test    edx, edx
0x18003bde7  jnz     short loc_18003BE01
0x18003bde9  lea     rax, [r15+rdi*8]
0x18003bded  mov     r9, r10
0x18003bdf0  mov     r8, rbp
0x18003bdf3  mov     [rsp+78h+var_50], rax
0x18003bdf8  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEB_W_K2PEAPEA_W@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,wchar_t const *,unsigned __int64,unsigned __int64,wchar_t * *)
0x18003bdfd  mov     ebx, eax
0x18003bdff  jmp     short loc_18003BE06
0x18003be01  mov     ebx, 80070057h
0x18003be06  mov     r8, [rsp+78h+arg_0]
0x18003be0e  xor     r10d, r10d
0x18003be11  mov     r9, [rsp+78h+var_48]
0x18003be16  lea     r11d, [r10+3]
0x18003be1a  test    ebx, ebx
0x18003be1c  js      short loc_18003BE2D
0x18003be1e  inc     rdi
0x18003be21  cmp     rdi, [rsp+78h+arg_10]
0x18003be29  cmovz   esi, r11d
0x18003be2d  cmp     r14, r8
0x18003be30  jnb     short loc_18003BE36
0x18003be32  add     r14, 2
0x18003be36  cmp     r13, r9
0x18003be39  jnb     short loc_18003BE3F
0x18003be3b  add     r13, 2
0x18003be3f  cmp     esi, 4
0x18003be42  jz      short loc_18003BE56
0x18003be44  test    ebx, ebx
0x18003be46  js      short loc_18003BE5B
0x18003be48  mov     edx, esi
0x18003be4a  jmp     loc_18003BCF9
0x18003be4f  mov     ebx, 80070057h
0x18003be54  jmp     short loc_18003BE2D
0x18003be56  mov     ebx, 80070057h
0x18003be5b  test    r15, r15
0x18003be5e  jnz     short loc_18003BE7A
0x18003be60  mov     rdi, r10
0x18003be63  jmp     short loc_18003BE88
0x18003be65  dec     rdi
0x18003be68  mov     rcx, [r15+rdi*8]; pv
0x18003be6c  call    cs:__imp_CoTaskMemFree
0x18003be72  mov     qword ptr [r15+rdi*8], 0
0x18003be7a  test    rdi, rdi
0x18003be7d  jnz     short loc_18003BE65
0x18003be7f  jmp     short loc_18003BE88
0x18003be81  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003be86  mov     ebx, eax
0x18003be88  mov     rcx, r12; pv
0x18003be8b  call    cs:__imp_CoTaskMemFree
0x18003be91  jmp     short loc_18003BE98
0x18003be93  mov     ebx, 80070216h
0x18003be98  mov     rax, [rsp+78h+arg_28]
0x18003bea0  mov     [rax], rdi
0x18003bea3  mov     eax, ebx
0x18003bea5  mov     rbx, [rsp+78h+arg_8]
0x18003bead  add     rsp, 40h
0x18003beb1  pop     r15
0x18003beb3  pop     r14
0x18003beb5  pop     r13
0x18003beb7  pop     r12
0x18003beb9  pop     rdi
0x18003beba  pop     rsi
0x18003bebb  pop     rbp
0x18003bebc  retn
```
