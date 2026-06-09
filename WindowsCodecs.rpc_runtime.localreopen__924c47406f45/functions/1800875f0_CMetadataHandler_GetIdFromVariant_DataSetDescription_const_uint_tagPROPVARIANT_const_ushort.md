# CMetadataHandler::GetIdFromVariant(DataSetDescription const *,uint,tagPROPVARIANT const *,ushort *)

- ea: `0x1800875f0`
- end: `0x180087779`
- name: `?GetIdFromVariant@CMetadataHandler@@MEAAJPEBUDataSetDescription@@IPEBUtagPROPVARIANT@@PEAG@Z`
- size: `393`
- prototype: `int(CMetadataHandler *__hidden this, const struct DataSetDescription *, unsigned int, const struct tagPROPVARIANT *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800874f0`
- `0x180087570`

## callees

- `0x1800875f0`
- `0x180087780`
- `0x18008cb54`
- `0x1800bb784`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800876dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800876dc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180087637`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180087637`
- `OLEAUT32!__imp_VariantInit` at `0x1800876a1`
- `OLEAUT32!__imp_VariantInit` at `0x1800876a1`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800876b8`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800876b8`

## pseudocode

```c
__int64 __fastcall CMetadataHandler::GetIdFromVariant(
        CMetadataHandler *this,
        const struct DataSetDescription *a2,
        unsigned int a3,
        const VARIANTARG *a4,
        unsigned __int16 *a5)
{
  unsigned __int16 *v5; // rdi
  const WCHAR *bstrVal; // rsi
  __int64 i; // rbx
  LPCWSTR *v11; // rdi
  unsigned int v12; // ebx
  bool v14; // zf
  int v15; // eax
  CMetadataHandler *v16; // rcx
  unsigned __int16 *DataSetDesc; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int16 *v19; // [rsp+78h] [rbp+20h] BYREF

  v5 = 0;
  v14 = a4->vt == 31;
  v19 = 0;
  if ( !v14 )
  {
    if ( a4->vt == 30 )
    {
      v15 = CoerceAnsiStrToWideStr(a4->pcVal, &v19);
      v12 = v15;
      if ( v15 < 0 )
      {
        if ( (_DWORD)g_doStackCaptures )
          DoStackCapture(v15);
        v5 = v19;
        goto LABEL_15;
      }
      v5 = v19;
      DataSetDesc = (unsigned __int16 *)CMetadataHandler::FindDataSetDesc(v16, a2, a3, v19);
      if ( !DataSetDesc )
      {
        v14 = (_DWORD)g_doStackCaptures == 0;
        v12 = -2147024809;
LABEL_17:
        if ( !v14 )
          DoStackCapture(v12);
        goto LABEL_15;
      }
      *a5 = *DataSetDesc;
    }
    else
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      if ( VariantChangeType(&pvarg, a4, 0, 0x12u) >= 0 )
      {
        v12 = 0;
        *a5 = pvarg.uiVal;
        goto LABEL_15;
      }
      v12 = -2003292352;
      if ( (_DWORD)g_doStackCaptures )
      {
        DoStackCapture(-2003292352);
        v14 = (_DWORD)g_doStackCaptures == 0;
        goto LABEL_17;
      }
    }
LABEL_15:
    if ( v5 )
      CoTaskMemFree(v5);
    return v12;
  }
  bstrVal = a4->bstrVal;
  if ( bstrVal )
  {
    for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
    {
      v11 = (LPCWSTR *)((char *)a2 + 24 * i);
      if ( !lstrcmpiW(bstrVal, v11[1]) )
      {
        if ( !v11 )
          break;
        v12 = 0;
        *a5 = *(_WORD *)v11;
        return v12;
      }
    }
  }
  v12 = -2147024809;
  if ( (_DWORD)g_doStackCaptures )
    DoStackCapture(-2147024809);
  return v12;
}

```

## disassembly

```asm
0x1800875f0  mov     [rsp+arg_0], rbx
0x1800875f5  mov     [rsp+arg_8], rbp
0x1800875fa  push    rsi
0x1800875fb  push    rdi
0x1800875fc  push    r14
0x1800875fe  sub     rsp, 40h
0x180087602  xor     edi, edi
0x180087604  mov     rbx, r9
0x180087607  cmp     word ptr [r9], 1Fh
0x18008760c  mov     ebp, r8d
0x18008760f  mov     r14, rdx
0x180087612  mov     [rsp+58h+arg_18], rdi
0x180087617  jnz     short loc_180087686
0x180087619  mov     rsi, [r9+8]
0x18008761d  test    rsi, rsi
0x180087620  jz      short loc_180087645
0x180087622  xor     ebx, ebx
0x180087624  cmp     ebx, ebp
0x180087626  jnb     short loc_180087645
0x180087628  lea     rcx, [rbx+rbx*2]
0x18008762c  lea     rdi, [r14+rcx*8]
0x180087630  mov     rcx, rsi; lpString1
0x180087633  mov     rdx, [rdi+8]; lpString2
0x180087637  call    cs:__imp_lstrcmpiW
0x18008763d  test    eax, eax
0x18008763f  jz      short loc_18008765C
0x180087641  inc     ebx
0x180087643  jmp     short loc_180087624
0x180087645  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18008764c  mov     ebx, 80070057h
0x180087651  jz      short loc_180087671
0x180087653  mov     ecx, ebx; int
0x180087655  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18008765a  jmp     short loc_180087671
0x18008765c  test    rdi, rdi
0x18008765f  jz      short loc_180087645
0x180087661  mov     rax, [rsp+58h+arg_20]
0x180087669  xor     ebx, ebx
0x18008766b  movzx   ecx, word ptr [rdi]
0x18008766e  mov     [rax], cx
0x180087671  mov     rbp, [rsp+58h+arg_8]
0x180087676  mov     eax, ebx
0x180087678  mov     rbx, [rsp+58h+arg_0]
0x18008767d  add     rsp, 40h
0x180087681  pop     r14
0x180087683  pop     rdi
0x180087684  pop     rsi
0x180087685  retn
0x180087686  cmp     word ptr [r9], 1Eh
0x18008768b  jz      short loc_1800876FE
0x18008768d  xorps   xmm0, xmm0
0x180087690  lea     rcx, [rsp+58h+pvarg]; pvarg
0x180087695  xor     eax, eax
0x180087697  movups  xmmword ptr [rsp+58h+pvarg], xmm0
0x18008769c  mov     qword ptr [rsp+58h+pvarg+10h], rax
0x1800876a1  call    cs:__imp_VariantInit
0x1800876a7  mov     r9d, 12h; vt
0x1800876ad  lea     rcx, [rsp+58h+pvarg]; pvargDest
0x1800876b2  xor     r8d, r8d; wFlags
0x1800876b5  mov     rdx, rbx; pvarSrc
0x1800876b8  call    cs:__imp_VariantChangeType
0x1800876be  test    eax, eax
0x1800876c0  js      short loc_180087728
0x1800876c2  mov     rdx, [rsp+58h+arg_20]
0x1800876ca  xor     ebx, ebx
0x1800876cc  movzx   eax, word ptr [rsp+58h+pvarg+8]
0x1800876d1  mov     [rdx], ax
0x1800876d4  test    rdi, rdi
0x1800876d7  jz      short loc_180087671
0x1800876d9  mov     rcx, rdi; pv
0x1800876dc  call    cs:__imp_CoTaskMemFree
0x1800876e2  jmp     short loc_180087671
0x1800876e4  mov     ecx, ebx; int
0x1800876e6  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800876eb  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800876f1  test    eax, eax
0x1800876f3  jz      short loc_1800876D4
0x1800876f5  mov     ecx, ebx; int
0x1800876f7  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800876fc  jmp     short loc_1800876D4
0x1800876fe  mov     rcx, [r9+8]; lpMultiByteStr
0x180087702  lea     rdx, [rsp+58h+arg_18]; unsigned __int16 **
0x180087707  call    ?CoerceAnsiStrToWideStr@@YAJPEBDPEAPEAGIH@Z; CoerceAnsiStrToWideStr(char const *,ushort * *,uint,int)
0x18008770c  mov     ebx, eax
0x18008770e  test    eax, eax
0x180087710  jns     short loc_18008773D
0x180087712  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180087718  jz      short loc_180087739
0x18008771a  mov     ecx, eax; int
0x18008771c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180087721  mov     rdi, [rsp+58h+arg_18]
0x180087726  jmp     short loc_1800876D4
0x180087728  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18008772e  mov     ebx, 88982F40h
0x180087733  test    eax, eax
0x180087735  jz      short loc_1800876D4
0x180087737  jmp     short loc_1800876E4
0x180087739  test    eax, eax
0x18008773b  js      short loc_180087721
0x18008773d  mov     rdi, [rsp+58h+arg_18]
0x180087742  mov     r8d, ebp; unsigned int
0x180087745  mov     r9, rdi; unsigned __int16 *
0x180087748  mov     rdx, r14; struct DataSetDescription *
0x18008774b  call    ?FindDataSetDesc@CMetadataHandler@@IEAAPEBUDataSetDescription@@PEBU2@IPEBG@Z; CMetadataHandler::FindDataSetDesc(DataSetDescription const *,uint,ushort const *)
0x180087750  test    rax, rax
0x180087753  jz      short loc_180087768
0x180087755  movzx   ecx, word ptr [rax]
0x180087758  mov     rax, [rsp+58h+arg_20]
0x180087760  mov     [rax], cx
0x180087763  jmp     loc_1800876D4
0x180087768  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18008776f  mov     ebx, 80070057h
0x180087774  jmp     loc_1800876F3
```
