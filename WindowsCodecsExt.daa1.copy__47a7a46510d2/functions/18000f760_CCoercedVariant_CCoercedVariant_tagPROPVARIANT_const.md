# CCoercedVariant::CCoercedVariant(tagPROPVARIANT const * *)

- ea: `0x18000f760`
- end: `0x18000f806`
- name: `??0CCoercedVariant@@QEAA@PEAPEBUtagPROPVARIANT@@@Z`
- size: `166`
- prototype: `CCoercedVariant *__fastcall(CCoercedVariant *__hidden this, const struct tagPROPVARIANT **)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f630`
- `0x180023ae0`
- `0x180023d10`

## callees

- `0x18000f760`
- `0x1800171c4`
- `0x18001d6e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f7a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f7a6`

## pseudocode

```c
CCoercedVariant *__fastcall CCoercedVariant::CCoercedVariant(
        CCoercedVariant *this,
        const struct tagPROPVARIANT **a2,
        __int64 a3,
        UINT a4)
{
  __int64 v5; // rax
  unsigned __int16 *v7; // rcx
  int v8; // edi
  int v10; // eax
  unsigned __int16 *v11; // [rsp+30h] [rbp+8h] BYREF

  *((_DWORD *)this + 6) = 0;
  *((_DWORD *)this + 7) = 1;
  *(_OWORD *)this = 0;
  *((_QWORD *)this + 2) = 0;
  v5 = (__int64)*a2;
  if ( *a2 )
  {
    v7 = 0;
    v8 = 0;
    v11 = 0;
    if ( *(_WORD *)v5 == 30 )
    {
      v10 = CoerceAnsiStrToWideStr(*(LPCCH *)(v5 + 8), &v11, a3, a4);
      v8 = v10;
      if ( v10 >= 0 )
      {
        v7 = 0;
        *((_QWORD *)this + 1) = v11;
        *(_WORD *)this = 31;
        *a2 = (const struct tagPROPVARIANT *)this;
      }
      else
      {
        if ( g_doStackCaptures )
          DoStackCapture(v10);
        v7 = v11;
      }
    }
    CoTaskMemFree(v7);
    *((_DWORD *)this + 6) = v8;
  }
  return this;
}

```

## disassembly

```asm
0x18000f760  mov     [rsp+arg_10], rbx
0x18000f765  push    rsi
0x18000f766  sub     rsp, 20h
0x18000f76a  mov     dword ptr [rcx+18h], 0
0x18000f771  xor     eax, eax
0x18000f773  mov     dword ptr [rcx+1Ch], 1
0x18000f77a  xorps   xmm0, xmm0
0x18000f77d  movups  xmmword ptr [rcx], xmm0
0x18000f780  mov     [rcx+10h], rax
0x18000f784  mov     rsi, rdx
0x18000f787  mov     rax, [rdx]
0x18000f78a  mov     rbx, rcx
0x18000f78d  test    rax, rax
0x18000f790  jz      short loc_18000F7B4
0x18000f792  xor     ecx, ecx; pv
0x18000f794  mov     [rsp+28h+arg_8], rdi
0x18000f799  xor     edi, edi
0x18000f79b  mov     [rsp+28h+arg_0], rcx
0x18000f7a0  cmp     word ptr [rax], 1Eh
0x18000f7a4  jz      short loc_18000F7C2
0x18000f7a6  call    cs:__imp_CoTaskMemFree
0x18000f7ac  mov     [rbx+18h], edi
0x18000f7af  mov     rdi, [rsp+28h+arg_8]
0x18000f7b4  mov     rax, rbx
0x18000f7b7  mov     rbx, [rsp+28h+arg_10]
0x18000f7bc  add     rsp, 20h
0x18000f7c0  pop     rsi
0x18000f7c1  retn
0x18000f7c2  mov     rcx, [rax+8]; lpMultiByteStr
0x18000f7c6  lea     rdx, [rsp+28h+arg_0]; unsigned __int16 **
0x18000f7cb  call    ?CoerceAnsiStrToWideStr@@YAJPEBDPEAPEAGIH@Z; CoerceAnsiStrToWideStr(char const *,ushort * *,uint,int)
0x18000f7d0  mov     edi, eax
0x18000f7d2  test    eax, eax
0x18000f7d4  jns     short loc_18000F7F1
0x18000f7d6  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000f7dd  jz      short loc_18000F7ED
0x18000f7df  mov     ecx, eax; int
0x18000f7e1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000f7e6  mov     rcx, [rsp+28h+arg_0]
0x18000f7eb  jmp     short loc_18000F7A6
0x18000f7ed  test    eax, eax
0x18000f7ef  js      short loc_18000F7E6
0x18000f7f1  mov     rax, [rsp+28h+arg_0]
0x18000f7f6  xor     ecx, ecx
0x18000f7f8  mov     [rbx+8], rax
0x18000f7fc  mov     word ptr [rbx], 1Fh
0x18000f801  mov     [rsi], rbx
0x18000f804  jmp     short loc_18000F7A6
```
