# CCookies::get_Item(tagVARIANT,tagVARIANT *)

- ea: `0x18004dec0`
- end: `0x18004e420`
- name: `?get_Item@CCookies@@UEAAJUtagVARIANT@@PEAU2@@Z`
- size: `1376`
- prototype: `int(CCookies *__hidden this, struct tagVARIANT *__struct_ptr, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, installer_update`

## callees

- `0x180002a38`
- `0x180006ed4`
- `0x180023d86`
- `0x180023dd0`
- `0x180039cf0`
- `0x18003a434`
- `0x18003a4cc`
- `0x18003a660`
- `0x1800406b0`
- `0x180049238`
- `0x18004ad4c`
- `0x18004ca64`
- `0x18004dec0`
- `0x180060bd4`
- `0x180061b54`
- `0x1800621bc`
- `0x180064010`

## import_xrefs

- `msvcrt!strchr` at `0x18004e16a`
- `msvcrt!strchr` at `0x18004e16a`
- `msvcrt!strcpy_s` at `0x18004e15f`
- `msvcrt!strcpy_s` at `0x18004e15f`
- `OLEAUT32!__imp_VariantInit` at `0x18004df55`
- `OLEAUT32!__imp_VariantInit` at `0x18004df72`
- `OLEAUT32!__imp_VariantInit` at `0x18004df55`
- `OLEAUT32!__imp_VariantInit` at `0x18004df72`
- `OLEAUT32!__imp_VariantClear` at `0x18004e3da`
- `OLEAUT32!__imp_VariantClear` at `0x18004e3da`
- `OLEAUT32!__imp_VariantChangeType` at `0x18004e22d`
- `OLEAUT32!__imp_VariantChangeType` at `0x18004e22d`
- `KERNEL32!GetACP` at `0x18004e000`
- `KERNEL32!GetACP` at `0x18004e1c3`
- `KERNEL32!GetACP` at `0x18004e269`
- `KERNEL32!GetACP` at `0x18004e357`
- `KERNEL32!GetACP` at `0x18004e000`
- `KERNEL32!GetACP` at `0x18004e1c3`
- `KERNEL32!GetACP` at `0x18004e269`
- `KERNEL32!GetACP` at `0x18004e357`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18004e331`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18004e331`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18004e0f8`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18004e0f8`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004e129`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18004e129`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18004df4c`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18004df4c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18004e3e5`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18004e3e5`

## pseudocode

```c
__int64 __fastcall CCookies::get_Item(CRequest **this, struct tagVARIANT *p_pvarg, struct tagVARIANT *a3)
{
  struct tagVARIANT *v4; // r12
  int Variables; // edi
  VARTYPE vt; // bx
  __int64 v9; // rcx
  char *PszCookie; // rax
  CRequest *v11; // rdi
  char *v12; // r15
  UINT ACP; // eax
  int v14; // r15d
  __int64 v15; // r14
  CCookie *v16; // rcx
  int v17; // ebx
  UINT v18; // r8d
  const CHAR *Ptr; // r13
  char *v20; // r14
  __int64 v21; // rdx
  __int64 v22; // rbx
  CCookie *v23; // r12
  char *v24; // rax
  char *HTTPCookie; // rax
  CRequest *v26; // rax
  UINT v27; // eax
  UINT v28; // eax
  __int64 v29; // rbx
  int v30; // eax
  UINT v31; // r8d
  const char *v32; // rdx
  struct CLinkElem *Elem; // rax
  __int64 lVal; // rax
  void (__fastcall ***v35)(_QWORD, GUID *, ULONG *); // rcx
  CCookie *v36; // rbx
  struct IUnknown *v37; // r9
  UINT v38; // r8d
  CCookie *v39; // rax
  CRequest *v40; // rcx
  void (*v41)(void); // [rsp+20h] [rbp-E0h]
  unsigned __int16 *p_vt; // [rsp+30h] [rbp-D0h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v44[48]; // [rsp+50h] [rbp-B0h] BYREF
  void *v45; // [rsp+80h] [rbp-80h] BYREF
  char v46; // [rsp+88h] [rbp-78h] BYREF
  int v47; // [rsp+188h] [rbp+88h]
  unsigned __int8 v48[128]; // [rsp+190h] [rbp+90h] BYREF

  p_vt = &a3->vt;
  v4 = a3;
  if ( (int)CRequest::CheckForTombstone(this[7]) < 0 )
    return 2147500037LL;
  v47 = 0;
  v45 = &v46;
  memset_0(v48, 0, sizeof(v48));
  BUFFER::BUFFER((BUFFER *)v44, v48, 0x80u);
  VariantInit(v4);
  Variables = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  switch ( p_pvarg->vt )
  {
    case 8u:
      vt = 8;
LABEL_11:
      v9 = *((_QWORD *)this[7] + 7);
      if ( (*(_BYTE *)(v9 + 320) & 4) != 0 )
      {
        PszCookie = CIsapiReqInfo::QueryPszCookie(*(CIsapiReqInfo **)(v9 + 48));
        v11 = this[7];
        v12 = PszCookie;
        ACP = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v11 + 7) + 56LL) + 164LL);
        if ( !ACP )
          ACP = GetACP();
        Variables = CRequest::LoadVariables(v11, 4u, v12, ACP);
        if ( Variables < 0 )
          goto LABEL_79;
        *(_DWORD *)(*((_QWORD *)this[7] + 7) + 320LL) &= ~4u;
      }
      if ( vt > 0x10u )
      {
        if ( vt != 17 && vt != 18 && vt != 19 && (unsigned int)vt - 20 >= 2 )
          goto LABEL_48;
      }
      else if ( vt != 16 && vt != 2 )
      {
        if ( vt == 3 )
          goto LABEL_50;
        if ( vt != 4 && vt != 5 )
        {
          if ( vt != 8 )
          {
            if ( vt == 10 && p_pvarg->lVal == -2147352572 )
            {
              v14 = 1;
              v15 = *(_QWORD *)(*((_QWORD *)this[7] + 7) + 80LL);
              if ( !v15 )
                goto LABEL_42;
              do
              {
                v16 = *(CCookie **)(v15 + 64);
                if ( v16 )
                {
                  v17 = *(_DWORD *)(v15 + 16);
                  v14 += v17 + CCookie::GetHTTPCookieSize(v16) + 1;
                }
                v15 = *(_QWORD *)(v15 + 32);
              }
              while ( v15 );
              if ( v14 <= 102400 )
              {
LABEL_42:
                if ( !BUFFER::Resize((BUFFER *)v44, v14) )
                  goto LABEL_33;
                Ptr = (const CHAR *)BUFFER::QueryPtr((BUFFER *)v44);
                v20 = (char *)Ptr;
                v21 = *((_QWORD *)this[7] + 7);
                v22 = *(_QWORD *)(v21 + 80);
                if ( v22 )
                {
                  do
                  {
                    v23 = *(CCookie **)(v22 + 64);
                    if ( v23 )
                    {
                      strcpy_s(v20, (rsize_t)&Ptr[(unsigned int)v14 - (_QWORD)v20], *(const char **)(v22 + 8));
                      v24 = strchr(v20, 0);
                      *v24 = 61;
                      HTTPCookie = CCookie::GetHTTPCookie(v23, v24 + 1, v14);
                      v20 = HTTPCookie;
                      if ( *(_QWORD *)(v22 + 32) )
                      {
                        *HTTPCookie = 59;
                        v20 = HTTPCookie + 1;
                      }
                    }
                    v22 = *(_QWORD *)(v22 + 32);
                  }
                  while ( v22 );
                  v4 = (struct tagVARIANT *)p_vt;
                }
                *v20 = 0;
                v26 = this[7];
                p_vt = 0;
                v27 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v26 + 7) + 56LL) + 164LL);
                if ( !v27 )
                  v27 = GetACP();
                if ( (int)SysAllocStringFromSz(Ptr, v21, &p_vt, v27) >= 0 )
                {
                  v4->llVal = (LONGLONG)p_vt;
                  v4->vt = 8;
                }
                else
                {
LABEL_33:
                  ExceptionId(&IID_IRequestDictionary, 0x1964u, 0x64u, 0);
                  Variables = -2147024882;
                }
                goto LABEL_79;
              }
              v18 = 107;
              goto LABEL_31;
            }
LABEL_48:
            v18 = 102;
LABEL_31:
            ExceptionId(&IID_IRequestDictionary, 0x1964u, v18, 0);
            Variables = -2147467259;
            goto LABEL_79;
          }
LABEL_50:
          v4->vt = 9;
          v4->llVal = 0;
          if ( vt == 8 )
          {
            v28 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this[7] + 7) + 56LL) + 164LL);
            if ( !v28 )
              v28 = GetACP();
            v29 = -1;
            v30 = CWCharToMBCS::Init((CWCharToMBCS *)&v45, p_pvarg->bstrVal, v28, -1);
            Variables = v30;
            if ( v30 >= 0 )
            {
              v32 = (const char *)v45;
            }
            else
            {
              if ( v30 == -2147024882 )
              {
                v31 = 100;
LABEL_78:
                ExceptionId(&IID_IRequestDictionary, 0x1964u, v31, 0);
                goto LABEL_79;
              }
              Variables = 0;
              v32 = Str1;
            }
            do
              ++v29;
            while ( v32[v29] );
            Elem = CHashTable::FindElem((CHashTable *)(*((_QWORD *)this[7] + 7) + 64LL), v32, v29);
          }
          else
          {
            lVal = p_pvarg->lVal;
            if ( (int)lVal < 1 || (int)lVal > *((_DWORD *)this + 8) || !*((_DWORD *)this + 8) )
            {
              Variables = -2147467259;
              v31 = 105;
              goto LABEL_78;
            }
            _mm_lfence();
            Elem = (struct CLinkElem *)*((_QWORD *)this[5] + lVal - 1);
          }
          if ( Elem )
          {
            v35 = (void (__fastcall ***)(_QWORD, GUID *, ULONG *))*((_QWORD *)Elem + 8);
            if ( v35 )
            {
              (**v35)(v35, &IID_IReadCookie, (ULONG *)&v4->cyVal);
              goto LABEL_79;
            }
          }
          if ( !this[13] )
          {
            v36 = (CCookie *)ALLOC_CACHE_HANDLER::Alloc(CCookie::sm_pach);
            if ( v36 )
            {
              v38 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this[7] + 7) + 56LL) + 164LL);
              if ( !v38 )
                v38 = GetACP();
              v39 = CCookie::CCookie(v36, *(struct CIsapiReqInfo **)(*((_QWORD *)this[7] + 7) + 48LL), v38, v37, v41);
              this[13] = v39;
              if ( v39 )
              {
                Variables = CCookie::Init(v39);
                goto LABEL_75;
              }
            }
            else
            {
              this[13] = 0;
            }
            Variables = -2147024882;
          }
LABEL_75:
          v40 = this[13];
          if ( v40 )
            Variables = (**(__int64 (__fastcall ***)(CRequest *, GUID *, __int64))v40)(
                          v40,
                          &IID_IReadCookie,
                          (__int64)&v4->llVal);
          goto LABEL_79;
        }
      }
      Variables = VariantChangeType(p_pvarg, p_pvarg, 0, 3u);
      if ( Variables < 0 )
        goto LABEL_79;
      goto LABEL_50;
    case 2u:
      vt = 2;
      goto LABEL_11;
    case 3u:
      vt = 3;
      goto LABEL_11;
  }
  if ( (int)VariantResolveDispatch(&pvarg, p_pvarg, &IID_IRequestDictionary, 0x1964u) >= 0 )
  {
    vt = pvarg.vt;
    p_pvarg = &pvarg;
    goto LABEL_11;
  }
LABEL_79:
  VariantClear(&pvarg);
  BUFFER::~BUFFER((BUFFER *)v44);
  CWCharToMBCS::~CWCharToMBCS((CWCharToMBCS *)&v45);
  return (unsigned int)Variables;
}

```

## disassembly

```asm
0x18004dec0  mov     [rsp-8+arg_18], rbx
0x18004dec5  push    rbp
0x18004dec6  push    rsi
0x18004dec7  push    rdi
0x18004dec8  push    r12
0x18004deca  push    r13
0x18004decc  push    r14
0x18004dece  push    r15
0x18004ded0  lea     rbp, [rsp-120h]
0x18004ded8  sub     rsp, 220h
0x18004dedf  mov     rax, cs:__security_cookie
0x18004dee6  xor     rax, rsp
0x18004dee9  mov     [rbp+150h+var_40], rax
0x18004def0  mov     rsi, rcx
0x18004def3  mov     [rsp+250h+var_220], r8
0x18004def8  mov     rcx, [rcx+38h]; this
0x18004defc  mov     r12, r8
0x18004deff  mov     r14, rdx
0x18004df02  call    ?CheckForTombstone@CRequest@@QEAAJXZ; CRequest::CheckForTombstone(void)
0x18004df07  xor     r13d, r13d
0x18004df0a  test    eax, eax
0x18004df0c  jns     short loc_18004DF18
0x18004df0e  mov     eax, 80004005h
0x18004df13  jmp     loc_18004E3F6
0x18004df18  lea     rax, [rbp+150h+var_1C8]
0x18004df1c  mov     [rbp+150h+var_C8], r13d
0x18004df23  mov     ebx, 80h
0x18004df28  mov     [rbp+150h+var_1D0], rax
0x18004df2c  mov     r8d, ebx; Size
0x18004df2f  lea     rcx, [rbp+150h+var_C0]; void *
0x18004df36  xor     edx, edx; Val
0x18004df38  call    memset_0
0x18004df3d  mov     r8d, ebx
0x18004df40  lea     rdx, [rbp+150h+var_C0]
0x18004df47  lea     rcx, [rsp+250h+var_200]
0x18004df4c  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18004df52  mov     rcx, r12; pvarg
0x18004df55  call    cs:__imp_VariantInit
0x18004df5b  xorps   xmm0, xmm0
0x18004df5e  lea     rcx, [rsp+250h+pvarg]; pvarg
0x18004df63  xor     eax, eax
0x18004df65  mov     edi, r13d
0x18004df68  movups  xmmword ptr [rsp+250h+pvarg], xmm0
0x18004df6d  mov     qword ptr [rsp+250h+pvarg+10h], rax
0x18004df72  call    cs:__imp_VariantInit
0x18004df78  lea     edx, [rbx-78h]
0x18004df7b  lea     ecx, [rbx-7Dh]
0x18004df7e  lea     eax, [rbx-7Eh]
0x18004df81  cmp     [r14], dx
0x18004df85  jz      short loc_18004DFCA
0x18004df87  cmp     [r14], ax
0x18004df8b  jz      short loc_18004DFC5
0x18004df8d  cmp     [r14], cx
0x18004df91  jz      short loc_18004DFC1
0x18004df93  mov     r9d, 1964h; unsigned int
0x18004df99  lea     r8, IID_IRequestDictionary; struct _GUID *
0x18004dfa0  mov     rdx, r14; pvargSrc
0x18004dfa3  lea     rcx, [rsp+250h+pvarg]; pvarg
0x18004dfa8  call    ?VariantResolveDispatch@@YAJPEAUtagVARIANT@@0AEBU_GUID@@H@Z; VariantResolveDispatch(tagVARIANT *,tagVARIANT *,_GUID const &,int)
0x18004dfad  test    eax, eax
0x18004dfaf  js      loc_18004E3D5
0x18004dfb5  movzx   ebx, word ptr [rsp+250h+pvarg]
0x18004dfba  lea     r14, [rsp+250h+pvarg]
0x18004dfbf  jmp     short loc_18004DFCD
0x18004dfc1  mov     ebx, ecx
0x18004dfc3  jmp     short loc_18004DFCD
0x18004dfc5  movzx   ebx, ax
0x18004dfc8  jmp     short loc_18004DFCD
0x18004dfca  movzx   ebx, dx
0x18004dfcd  mov     rax, [rsi+38h]
0x18004dfd1  mov     rcx, [rax+38h]
0x18004dfd5  test    byte ptr [rcx+140h], 4
0x18004dfdc  jz      short loc_18004E032
0x18004dfde  mov     rcx, [rcx+30h]; this
0x18004dfe2  call    ?QueryPszCookie@CIsapiReqInfo@@QEAAPEADXZ; CIsapiReqInfo::QueryPszCookie(void)
0x18004dfe7  mov     rdi, [rsi+38h]
0x18004dfeb  mov     r15, rax
0x18004dfee  mov     rcx, [rdi+38h]
0x18004dff2  mov     rdx, [rcx+38h]
0x18004dff6  mov     eax, [rdx+0A4h]
0x18004dffc  test    eax, eax
0x18004dffe  jnz     short loc_18004E006
0x18004e000  call    cs:__imp_GetACP
0x18004e006  mov     r9d, eax
0x18004e009  mov     r8, r15
0x18004e00c  mov     edx, 4
0x18004e011  mov     rcx, rdi
0x18004e014  call    ?LoadVariables@CRequest@@AEAAJW4CollectionType@@PEADI@Z; CRequest::LoadVariables(CollectionType,char *,uint)
0x18004e019  mov     edi, eax
0x18004e01b  test    eax, eax
0x18004e01d  js      loc_18004E3D5
0x18004e023  mov     rcx, [rsi+38h]
0x18004e027  mov     rdx, [rcx+38h]
0x18004e02b  and     dword ptr [rdx+140h], 0FFFFFFFBh
0x18004e032  movzx   r15d, bx
0x18004e036  cmp     bx, 10h
0x18004e03a  ja      loc_18004E1F7
0x18004e040  jz      loc_18004E21E
0x18004e046  mov     eax, r15d
0x18004e049  sub     eax, 2
0x18004e04c  jz      loc_18004E21E
0x18004e052  sub     eax, 1
0x18004e055  jz      loc_18004E23D
0x18004e05b  sub     eax, 1
0x18004e05e  jz      loc_18004E21E
0x18004e064  sub     eax, 1
0x18004e067  jz      loc_18004E21E
0x18004e06d  sub     eax, 3
0x18004e070  jz      loc_18004E23D
0x18004e076  cmp     eax, 2
0x18004e079  jnz     loc_18004E213
0x18004e07f  cmp     dword ptr [r14+8], 80020004h
0x18004e087  jnz     loc_18004E213
0x18004e08d  lea     r15d, [rax-1]
0x18004e091  mov     rax, [rsi+38h]
0x18004e095  mov     rcx, [rax+38h]
0x18004e099  mov     r14, [rcx+50h]
0x18004e09d  test    r14, r14
0x18004e0a0  jz      short loc_18004E0F0
0x18004e0a2  mov     rcx, [r14+40h]; this
0x18004e0a6  test    rcx, rcx
0x18004e0a9  jz      short loc_18004E0BC
0x18004e0ab  mov     ebx, [r14+10h]
0x18004e0af  call    ?GetHTTPCookieSize@CCookie@@QEAA_KXZ; CCookie::GetHTTPCookieSize(void)
0x18004e0b4  add     eax, ebx
0x18004e0b6  inc     r15d
0x18004e0b9  add     r15d, eax
0x18004e0bc  mov     r14, [r14+20h]
0x18004e0c0  test    r14, r14
0x18004e0c3  jnz     short loc_18004E0A2
0x18004e0c5  cmp     r15d, 19000h
0x18004e0cc  jle     short loc_18004E0F0
0x18004e0ce  lea     r8d, [r14+6Bh]; unsigned int
0x18004e0d2  mov     edx, 1964h; unsigned int
0x18004e0d7  lea     rcx, IID_IRequestDictionary; struct _GUID *
0x18004e0de  xor     r9d, r9d; int
0x18004e0e1  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x18004e0e6  mov     edi, 80004005h
0x18004e0eb  jmp     loc_18004E3D5
0x18004e0f0  mov     edx, r15d
0x18004e0f3  lea     rcx, [rsp+250h+var_200]
0x18004e0f8  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18004e0fe  test    al, al
0x18004e100  jnz     short loc_18004E124
0x18004e102  xor     r9d, r9d; int
0x18004e105  lea     rcx, IID_IRequestDictionary; struct _GUID *
0x18004e10c  mov     edx, 1964h; unsigned int
0x18004e111  lea     r8d, [r9+64h]; unsigned int
0x18004e115  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x18004e11a  mov     edi, 8007000Eh
0x18004e11f  jmp     loc_18004E3D5
0x18004e124  lea     rcx, [rsp+250h+var_200]
0x18004e129  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18004e12f  mov     rcx, [rsi+38h]
0x18004e133  mov     r13, rax
0x18004e136  mov     r14, rax
0x18004e139  mov     rdx, [rcx+38h]
0x18004e13d  mov     rbx, [rdx+50h]
0x18004e141  test    rbx, rbx
0x18004e144  jz      short loc_18004E1A0
0x18004e146  mov     r12, [rbx+40h]
0x18004e14a  test    r12, r12
0x18004e14d  jz      short loc_18004E192
0x18004e14f  mov     r8, [rbx+8]; Source
0x18004e153  mov     rcx, r14; Destination
0x18004e156  mov     edx, r15d
0x18004e159  sub     rdx, r14
0x18004e15c  add     rdx, r13; SizeInBytes
0x18004e15f  call    cs:__imp_strcpy_s
0x18004e165  xor     edx, edx; Val
0x18004e167  mov     rcx, r14; Str
0x18004e16a  call    cs:__imp_strchr
0x18004e170  mov     r8d, r15d; int
0x18004e173  mov     rcx, r12; this
0x18004e176  lea     rdx, [rax+1]; char *
0x18004e17a  mov     byte ptr [rax], 3Dh ; '='
0x18004e17d  call    ?GetHTTPCookie@CCookie@@QEAAPEADPEADH@Z; CCookie::GetHTTPCookie(char *,int)
0x18004e182  cmp     qword ptr [rbx+20h], 0
0x18004e187  mov     r14, rax
0x18004e18a  jz      short loc_18004E192
0x18004e18c  mov     byte ptr [rax], 3Bh ; ';'
0x18004e18f  inc     r14
0x18004e192  mov     rbx, [rbx+20h]
0x18004e196  test    rbx, rbx
0x18004e199  jnz     short loc_18004E146
0x18004e19b  mov     r12, [rsp+250h+var_220]
0x18004e1a0  mov     byte ptr [r14], 0
0x18004e1a4  mov     rax, [rsi+38h]
0x18004e1a8  mov     [rsp+250h+var_220], 0
0x18004e1b1  mov     rcx, [rax+38h]
0x18004e1b5  mov     rax, [rcx+38h]
0x18004e1b9  mov     eax, [rax+0A4h]
0x18004e1bf  test    eax, eax
0x18004e1c1  jnz     short loc_18004E1C9
0x18004e1c3  call    cs:__imp_GetACP
0x18004e1c9  mov     r9d, eax; unsigned int
0x18004e1cc  lea     r8, [rsp+250h+var_220]; unsigned __int16 **
0x18004e1d1  mov     rcx, r13; lpMultiByteStr
0x18004e1d4  call    ?SysAllocStringFromSz@@YAJPEADKPEAPEAGI@Z; SysAllocStringFromSz(char *,ulong,ushort * *,uint)
0x18004e1d9  test    eax, eax
0x18004e1db  js      loc_18004E102
0x18004e1e1  mov     rax, [rsp+250h+var_220]
0x18004e1e6  mov     [r12+8], rax
0x18004e1eb  mov     word ptr [r12], 8
0x18004e1f2  jmp     loc_18004E3D5
0x18004e1f7  mov     eax, r15d
0x18004e1fa  sub     eax, 11h
0x18004e1fd  jz      short loc_18004E21E
0x18004e1ff  sub     eax, 1
0x18004e202  jz      short loc_18004E21E
0x18004e204  sub     eax, 1
0x18004e207  jz      short loc_18004E21E
0x18004e209  sub     eax, 1
0x18004e20c  jz      short loc_18004E21E
0x18004e20e  cmp     eax, 1
0x18004e211  jz      short loc_18004E21E
0x18004e213  mov     r8d, 66h ; 'f'
0x18004e219  jmp     loc_18004E0D2
0x18004e21e  mov     r9d, 3; vt
0x18004e224  xor     r8d, r8d; wFlags
0x18004e227  mov     rdx, r14; pvarSrc
0x18004e22a  mov     rcx, r14; pvargDest
0x18004e22d  call    cs:__imp_VariantChangeType
0x18004e233  mov     edi, eax
0x18004e235  test    eax, eax
0x18004e237  js      loc_18004E3D5
0x18004e23d  mov     eax, 8
0x18004e242  mov     word ptr [r12], 9
0x18004e249  mov     [r12+8], r13
0x18004e24e  cmp     r15d, eax
0x18004e251  jnz     short loc_18004E2CB
0x18004e253  mov     rax, [rsi+38h]
0x18004e257  mov     rcx, [rax+38h]
0x18004e25b  mov     rax, [rcx+38h]
0x18004e25f  mov     eax, [rax+0A4h]
0x18004e265  test    eax, eax
0x18004e267  jnz     short loc_18004E26F
0x18004e269  call    cs:__imp_GetACP
0x18004e26f  mov     rdx, [r14+8]; unsigned __int16 *
0x18004e273  lea     rcx, [rbp+150h+var_1D0]; this
0x18004e277  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004e27b  mov     r8d, eax; unsigned int
0x18004e27e  mov     r9d, ebx; int
0x18004e281  call    ?Init@CWCharToMBCS@@QEAAJPEBGIH@Z; CWCharToMBCS::Init(ushort const *,uint,int)
0x18004e286  mov     edi, eax
0x18004e288  test    eax, eax
0x18004e28a  jns     short loc_18004E2A8
0x18004e28c  cmp     eax, 8007000Eh
0x18004e291  jnz     short loc_18004E29C
0x18004e293  lea     r8d, [rbx+65h]
0x18004e297  jmp     loc_18004E3C1
0x18004e29c  mov     edi, r13d
0x18004e29f  lea     rdx, Str1
0x18004e2a6  jmp     short loc_18004E2AC
0x18004e2a8  mov     rdx, [rbp+150h+var_1D0]; void *
0x18004e2ac  mov     rax, [rsi+38h]
0x18004e2b0  mov     rcx, [rax+38h]
0x18004e2b4  add     rcx, 40h ; '@'; this
0x18004e2b8  inc     rbx
0x18004e2bb  cmp     [rdx+rbx], r13b
0x18004e2bf  jnz     short loc_18004E2B8
0x18004e2c1  mov     r8d, ebx; int
0x18004e2c4  call    ?FindElem@CHashTable@@QEAAPEAUCLinkElem@@PEBXH@Z; CHashTable::FindElem(void const *,int)
0x18004e2c9  jmp     short loc_18004E2FA
0x18004e2cb  movsxd  rax, dword ptr [r14+8]
0x18004e2cf  cmp     eax, 1
0x18004e2d2  jl      loc_18004E3B6
0x18004e2d8  cmp     eax, [rsi+20h]
0x18004e2db  jg      loc_18004E3B6
0x18004e2e1  cmp     [rsi+20h], r13d
0x18004e2e5  jz      loc_18004E3B6
0x18004e2eb  lfence
0x18004e2ee  mov     rcx, rax
0x18004e2f1  mov     rax, [rsi+28h]
0x18004e2f5  mov     rax, [rax+rcx*8-8]
0x18004e2fa  test    rax, rax
0x18004e2fd  jz      short loc_18004E324
0x18004e2ff  mov     rcx, [rax+40h]
0x18004e303  test    rcx, rcx
0x18004e306  jz      short loc_18004E324
0x18004e308  mov     rax, [rcx]
0x18004e30b  lea     r8, [r12+8]
0x18004e310  lea     rdx, IID_IReadCookie
0x18004e317  mov     rax, [rax]
0x18004e31a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e31f  jmp     loc_18004E3D5
0x18004e324  cmp     [rsi+68h], r13
0x18004e328  jnz     short loc_18004E392
0x18004e32a  mov     rcx, cs:?sm_pach@CCookie@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CCookie::sm_pach
0x18004e331  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18004e337  mov     rbx, rax
0x18004e33a  test    rax, rax
0x18004e33d  jz      short loc_18004E389
0x18004e33f  mov     rcx, [rsi+38h]
0x18004e343  mov     rdx, [rcx+38h]
0x18004e347  mov     rcx, [rdx+38h]
0x18004e34b  mov     r8d, [rcx+0A4h]
0x18004e352  test    r8d, r8d
0x18004e355  jnz     short loc_18004E360
0x18004e357  call    cs:__imp_GetACP
  ... truncated ...
```
