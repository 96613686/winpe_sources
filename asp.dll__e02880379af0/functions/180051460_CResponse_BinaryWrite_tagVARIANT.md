# CResponse::BinaryWrite(tagVARIANT)

- ea: `0x180051460`
- end: `0x18005163a`
- name: `?BinaryWrite@CResponse@@UEAAJUtagVARIANT@@@Z`
- size: `474`
- prototype: `__int64 __fastcall(CResponse *__hidden this, VARIANTARG *pvargSrc)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180017ac0`
- `0x180019050`
- `0x180019090`
- `0x1800406b0`
- `0x180051460`
- `0x180051664`
- `0x1800621bc`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180051625`
- `OLEAUT32!__imp_VariantClear` at `0x180051625`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800514ed`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800514ed`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18005154c`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18005154c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180051581`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180051581`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18005156e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18005156e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180051592`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180051592`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800515da`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005160e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180051619`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800515da`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005160e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180051619`

## pseudocode

```c
__int64 __fastcall CResponse::BinaryWrite(CResponseData **this, VARIANTARG *pvargSrc)
{
  HRESULT v5; // ebx
  CResponseData *v6; // rax
  HRESULT v7; // eax
  int v8; // r8d
  bool v9; // zf
  unsigned int v10; // r8d
  SAFEARRAY *parray; // rdi
  int v12; // eax
  unsigned int v13; // r8d
  CResponseBuffer *v14; // r10
  void *ppvData; // [rsp+30h] [rbp-20h] BYREF
  VARIANTARG pvargDest; // [rsp+38h] [rbp-18h] BYREF
  LONG plUbound; // [rsp+80h] [rbp+30h] BYREF
  LONG plLbound; // [rsp+88h] [rbp+38h] BYREF

  if ( (int)CResponse::CheckForTombstone((CResponse *)this) < 0 )
    return 2147500037LL;
  v5 = 0;
  v6 = this[7];
  plLbound = 0;
  plUbound = 0;
  ppvData = 0;
  memset(&pvargDest, 0, sizeof(pvargDest));
  if ( (*((_BYTE *)v6 + 280) & 6) == 0 )
  {
    v5 = VariantResolveDispatch(&pvargDest, pvargSrc, &IID_IResponse, 0x1770u);
    if ( v5 >= 0 )
    {
      if ( pvargDest.vt == 8209 || (v7 = VariantChangeType(&pvargDest, &pvargDest, 0, 0x2011u), v5 = v7, v7 >= 0) )
      {
        parray = pvargDest.parray;
        if ( SafeArrayGetDim(pvargDest.parray) != 1
          || SafeArrayGetLBound(parray, 1u, &plLbound) < 0
          || SafeArrayGetUBound(parray, 1u, &plUbound) < 0
          || SafeArrayAccessData(parray, &ppvData) < 0 )
        {
          v5 = -2147024809;
          goto LABEL_25;
        }
        v12 = CResponseData::FChunkData(this[7]);
        v5 = CResponseBuffer::Write(v14, (char *)ppvData, v13, v12, 0);
        if ( v5 >= 0 )
        {
          if ( (*((_BYTE *)this[7] + 280) & 8) != 0 || (v5 = CResponse::WriteResponse((CResponse *)this, 0), v5 >= 0) )
            v5 = SafeArrayUnaccessData(parray);
          else
            SafeArrayUnaccessData(parray);
          goto LABEL_25;
        }
        SafeArrayUnaccessData(parray);
        v8 = 0;
        v9 = v5 == -2147024882;
      }
      else
      {
        if ( v7 == -2147352571 )
        {
          v10 = 106;
          goto LABEL_13;
        }
        if ( v7 == -2147352566 )
        {
          v5 = -2147467259;
          v10 = 6010;
          goto LABEL_13;
        }
        v8 = 0;
        v9 = v7 == -2147024882;
      }
      LOBYTE(v8) = !v9;
      v10 = v8 + 100;
LABEL_13:
      ExceptionId(&IID_IResponse, 0x1770u, v10, 0);
LABEL_25:
      VariantClear(&pvargDest);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180051460  mov     [rsp-18h+arg_0], rbx
0x180051465  push    rbp
0x180051466  push    rsi
0x180051467  push    rdi
0x180051468  mov     rbp, rsp
0x18005146b  sub     rsp, 50h
0x18005146f  mov     rdi, rdx
0x180051472  mov     rsi, rcx
0x180051475  call    ?CheckForTombstone@CResponse@@QEAAJXZ; CResponse::CheckForTombstone(void)
0x18005147a  test    eax, eax
0x18005147c  jns     short loc_180051488
0x18005147e  mov     eax, 80004005h
0x180051483  jmp     loc_18005162D
0x180051488  xor     ebx, ebx
0x18005148a  xor     eax, eax
0x18005148c  mov     qword ptr [rbp+pvargDest+10h], rax
0x180051490  xorps   xmm0, xmm0
0x180051493  mov     rax, [rsi+38h]
0x180051497  mov     [rbp+plLbound], ebx
0x18005149a  mov     [rbp+plUbound], ebx
0x18005149d  mov     [rbp+ppvData], rbx
0x1800514a1  movups  xmmword ptr [rbp+pvargDest], xmm0
0x1800514a5  test    byte ptr [rax+118h], 6
0x1800514ac  jnz     loc_18005162B
0x1800514b2  mov     r9d, 1770h; unsigned int
0x1800514b8  lea     r8, IID_IResponse; struct _GUID *
0x1800514bf  mov     rdx, rdi; pvargSrc
0x1800514c2  lea     rcx, [rbp+pvargDest]; pvarg
0x1800514c6  call    ?VariantResolveDispatch@@YAJPEAUtagVARIANT@@0AEBU_GUID@@H@Z; VariantResolveDispatch(tagVARIANT *,tagVARIANT *,_GUID const &,int)
0x1800514cb  mov     ebx, eax
0x1800514cd  test    eax, eax
0x1800514cf  js      loc_18005162B
0x1800514d5  mov     r9d, 2011h; vt
0x1800514db  cmp     word ptr [rbp+pvargDest], r9w
0x1800514e0  jz      short loc_180051545
0x1800514e2  xor     r8d, r8d; wFlags
0x1800514e5  lea     rdx, [rbp+pvargDest]; pvarSrc
0x1800514e9  lea     rcx, [rbp+pvargDest]; pvargDest
0x1800514ed  call    cs:__imp_VariantChangeType
0x1800514f3  mov     ebx, eax
0x1800514f5  test    eax, eax
0x1800514f7  jns     short loc_180051545
0x1800514f9  cmp     eax, 80020005h
0x1800514fe  jz      short loc_180051526
0x180051500  cmp     eax, 8002000Ah
0x180051505  jz      short loc_180051519
0x180051507  xor     r8d, r8d
0x18005150a  cmp     eax, 8007000Eh
0x18005150f  setnz   r8b
0x180051513  add     r8d, 64h ; 'd'
0x180051517  jmp     short loc_18005152C
0x180051519  mov     ebx, 80004005h
0x18005151e  mov     r8d, 177Ah
0x180051524  jmp     short loc_18005152C
0x180051526  mov     r8d, 6Ah ; 'j'; unsigned int
0x18005152c  xor     r9d, r9d; int
0x18005152f  lea     rcx, IID_IResponse; struct _GUID *
0x180051536  mov     edx, 1770h; unsigned int
0x18005153b  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x180051540  jmp     loc_180051621
0x180051545  mov     rdi, qword ptr [rbp+pvargDest+8]
0x180051549  mov     rcx, rdi; psa
0x18005154c  call    cs:__imp_SafeArrayGetDim
0x180051552  mov     ebx, 1
0x180051557  cmp     eax, ebx
0x180051559  jz      short loc_180051565
0x18005155b  mov     ebx, 80070057h
0x180051560  jmp     loc_180051621
0x180051565  lea     r8, [rbp+plLbound]; plLbound
0x180051569  mov     edx, ebx; nDim
0x18005156b  mov     rcx, rdi; psa
0x18005156e  call    cs:__imp_SafeArrayGetLBound
0x180051574  test    eax, eax
0x180051576  js      short loc_18005155B
0x180051578  lea     r8, [rbp+plUbound]; plUbound
0x18005157c  mov     edx, ebx; nDim
0x18005157e  mov     rcx, rdi; psa
0x180051581  call    cs:__imp_SafeArrayGetUBound
0x180051587  test    eax, eax
0x180051589  js      short loc_18005155B
0x18005158b  lea     rdx, [rbp+ppvData]; ppvData
0x18005158f  mov     rcx, rdi; psa
0x180051592  call    cs:__imp_SafeArrayAccessData
0x180051598  test    eax, eax
0x18005159a  js      short loc_18005155B
0x18005159c  mov     rcx, [rsi+38h]; this
0x1800515a0  mov     r8d, [rbp+plUbound]
0x1800515a4  sub     r8d, [rbp+plLbound]
0x1800515a8  inc     r8d
0x1800515ab  mov     rax, [rcx+98h]
0x1800515b2  mov     r10, [rax]
0x1800515b5  call    ?FChunkData@CResponseData@@QEAAHXZ; CResponseData::FChunkData(void)
0x1800515ba  mov     rdx, [rbp+ppvData]; char *
0x1800515be  mov     r9d, eax; int
0x1800515c1  mov     rcx, r10; this
0x1800515c4  mov     [rsp+50h+var_30], 0; int
0x1800515cc  call    ?Write@CResponseBuffer@@QEAAJPEADKHH@Z; CResponseBuffer::Write(char *,ulong,int,int)
0x1800515d1  mov     ebx, eax
0x1800515d3  test    eax, eax
0x1800515d5  jns     short loc_1800515EE
0x1800515d7  mov     rcx, rdi; psa
0x1800515da  call    cs:__imp_SafeArrayUnaccessData
0x1800515e0  xor     r8d, r8d
0x1800515e3  cmp     ebx, 8007000Eh
0x1800515e9  jmp     loc_18005150F
0x1800515ee  mov     rax, [rsi+38h]
0x1800515f2  test    byte ptr [rax+118h], 8
0x1800515f9  jnz     short loc_180051616
0x1800515fb  xor     edx, edx; int
0x1800515fd  mov     rcx, rsi; this
0x180051600  call    ?WriteResponse@CResponse@@QEAAJH@Z; CResponse::WriteResponse(int)
0x180051605  mov     ebx, eax
0x180051607  test    eax, eax
0x180051609  jns     short loc_180051616
0x18005160b  mov     rcx, rdi; psa
0x18005160e  call    cs:__imp_SafeArrayUnaccessData
0x180051614  jmp     short loc_180051621
0x180051616  mov     rcx, rdi; psa
0x180051619  call    cs:__imp_SafeArrayUnaccessData
0x18005161f  mov     ebx, eax
0x180051621  lea     rcx, [rbp+pvargDest]; pvarg
0x180051625  call    cs:__imp_VariantClear
0x18005162b  mov     eax, ebx
0x18005162d  mov     rbx, [rsp+50h+arg_0]
0x180051632  add     rsp, 50h
0x180051636  pop     rdi
0x180051637  pop     rsi
0x180051638  pop     rbp
0x180051639  retn
```
