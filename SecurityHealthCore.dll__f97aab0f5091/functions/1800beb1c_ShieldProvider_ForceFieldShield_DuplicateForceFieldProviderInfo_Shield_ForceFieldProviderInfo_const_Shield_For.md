# ShieldProvider::ForceFieldShield::DuplicateForceFieldProviderInfo(Shield_ForceFieldProviderInfo const *,Shield_ForceFieldProviderInfo *)

- ea: `0x1800beb1c`
- end: `0x1800bebd1`
- name: `?DuplicateForceFieldProviderInfo@ForceFieldShield@ShieldProvider@@CAJPEBUShield_ForceFieldProviderInfo@@PEAU3@@Z`
- size: `181`
- prototype: `static int(const struct Shield_ForceFieldProviderInfo *, struct Shield_ForceFieldProviderInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800bee90`

## callees

- `0x18000517c`
- `0x1800beb1c`
- `0x1800e1764`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800beb9e`
- `ole32!CoTaskMemFree` at `0x1800beba8`
- `ole32!CoTaskMemFree` at `0x1800bebb2`
- `ole32!CoTaskMemFree` at `0x1800beb9e`
- `ole32!CoTaskMemFree` at `0x1800beba8`
- `ole32!CoTaskMemFree` at `0x1800bebb2`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ForceFieldShield::DuplicateForceFieldProviderInfo(
        const struct Shield_ForceFieldProviderInfo *a1,
        struct Shield_ForceFieldProviderInfo *a2,
        unsigned __int16 *a3)
{
  int v4; // edi
  unsigned __int16 **v6; // rdx
  unsigned __int16 **v7; // rdx
  unsigned __int16 **v8; // rdx

  v4 = 0;
  *(_OWORD *)a2 = *(_OWORD *)a1;
  *((_DWORD *)a2 + 14) = *((_DWORD *)a1 + 14);
  *((_DWORD *)a2 + 10) = *((_DWORD *)a1 + 10);
  *((_DWORD *)a2 + 11) = *((_DWORD *)a1 + 11);
  *((_DWORD *)a2 + 12) = *((_DWORD *)a1 + 12);
  *((_DWORD *)a2 + 13) = *((_DWORD *)a1 + 13);
  v6 = (unsigned __int16 **)*((_QWORD *)a1 + 2);
  if ( v6 )
  {
    v4 = CommonUtil::UtilCoDuplicateString((struct Shield_ForceFieldProviderInfo *)((char *)a2 + 16), v6, a3);
    if ( v4 < 0 )
      goto LABEL_8;
  }
  v7 = (unsigned __int16 **)*((_QWORD *)a1 + 3);
  if ( v7 )
  {
    v4 = CommonUtil::UtilCoDuplicateString((struct Shield_ForceFieldProviderInfo *)((char *)a2 + 24), v7, a3);
    if ( v4 < 0 )
      goto LABEL_8;
  }
  v8 = (unsigned __int16 **)*((_QWORD *)a1 + 4);
  if ( v8 )
    v4 = CommonUtil::UtilCoDuplicateString((struct Shield_ForceFieldProviderInfo *)((char *)a2 + 32), v8, a3);
  if ( v4 < 0 )
  {
LABEL_8:
    CoTaskMemFree(*((LPVOID *)a2 + 2));
    CoTaskMemFree(*((LPVOID *)a2 + 3));
    CoTaskMemFree(*((LPVOID *)a2 + 4));
    memset_0(a2, 0, 0x40u);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800beb1c  push    rbx
0x1800beb1e  push    rbp
0x1800beb1f  push    rsi
0x1800beb20  push    rdi
0x1800beb21  sub     rsp, 28h
0x1800beb25  movups  xmm0, xmmword ptr [rcx]
0x1800beb28  mov     rsi, rdx
0x1800beb2b  xor     edi, edi
0x1800beb2d  mov     rbp, rcx
0x1800beb30  movdqu  xmmword ptr [rdx], xmm0
0x1800beb34  mov     eax, [rcx+38h]
0x1800beb37  mov     [rdx+38h], eax
0x1800beb3a  mov     eax, [rcx+28h]
0x1800beb3d  mov     [rdx+28h], eax
0x1800beb40  mov     eax, [rcx+2Ch]
0x1800beb43  mov     [rdx+2Ch], eax
0x1800beb46  mov     eax, [rcx+30h]
0x1800beb49  mov     [rdx+30h], eax
0x1800beb4c  mov     eax, [rcx+34h]
0x1800beb4f  mov     [rdx+34h], eax
0x1800beb52  mov     rdx, [rcx+10h]; unsigned __int16 **
0x1800beb56  test    rdx, rdx
0x1800beb59  jz      short loc_1800BEB6A
0x1800beb5b  lea     rcx, [rsi+10h]; this
0x1800beb5f  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800beb64  mov     edi, eax
0x1800beb66  test    eax, eax
0x1800beb68  js      short loc_1800BEB9A
0x1800beb6a  mov     rdx, [rbp+18h]; unsigned __int16 **
0x1800beb6e  test    rdx, rdx
0x1800beb71  jz      short loc_1800BEB82
0x1800beb73  lea     rcx, [rsi+18h]; this
0x1800beb77  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800beb7c  mov     edi, eax
0x1800beb7e  test    eax, eax
0x1800beb80  js      short loc_1800BEB9A
0x1800beb82  mov     rdx, [rbp+20h]; unsigned __int16 **
0x1800beb86  test    rdx, rdx
0x1800beb89  jz      short loc_1800BEB96
0x1800beb8b  lea     rcx, [rsi+20h]; this
0x1800beb8f  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800beb94  mov     edi, eax
0x1800beb96  test    edi, edi
0x1800beb98  jns     short loc_1800BEBC6
0x1800beb9a  mov     rcx, [rsi+10h]; pv
0x1800beb9e  call    cs:__imp_CoTaskMemFree
0x1800beba4  mov     rcx, [rsi+18h]; pv
0x1800beba8  call    cs:__imp_CoTaskMemFree
0x1800bebae  mov     rcx, [rsi+20h]; pv
0x1800bebb2  call    cs:__imp_CoTaskMemFree
0x1800bebb8  xor     edx, edx; Val
0x1800bebba  mov     rcx, rsi; void *
0x1800bebbd  lea     r8d, [rdx+40h]; Size
0x1800bebc1  call    memset_0
0x1800bebc6  mov     eax, edi
0x1800bebc8  add     rsp, 28h
0x1800bebcc  pop     rdi
0x1800bebcd  pop     rsi
0x1800bebce  pop     rbp
0x1800bebcf  pop     rbx
0x1800bebd0  retn
```
