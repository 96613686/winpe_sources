# _lambda_02b35675a306e9de2db5614b6aeb3d1a_::operator()

- ea: `0x18000c0cc`
- end: `0x18000c153`
- name: `_lambda_02b35675a306e9de2db5614b6aeb3d1a_::operator()`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000bb58`
- `0x180013fdc`

## callees

- `0x180001008`
- `0x18000c0cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000c0e4`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000c0e4`

## pseudocode

```c
int __fastcall lambda_02b35675a306e9de2db5614b6aeb3d1a_::operator()(__int64 a1)
{
  _BYTE *v1; // rax
  int v3; // r9d
  int v5; // [rsp+40h] [rbp+8h] BYREF
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  v1 = *(_BYTE **)a1;
  if ( **(_BYTE **)a1 )
  {
    LODWORD(v1) = GetProcessId(**(HANDLE **)(a1 + 8));
    if ( (unsigned int)dword_18003B0F8 > 3
      && (qword_18003B108 & 0x400000000000LL) != 0
      && (qword_18003B110 & 0x400000000000LL) == qword_18003B110 )
    {
      v5 = (int)v1;
      v6 = **(_QWORD **)(a1 + 16);
      LODWORD(v1) = _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                      v6,
                      (unsigned int)byte_1800357A9,
                      0,
                      v3,
                      (__int64)&v6,
                      (__int64)&v5);
    }
  }
  return (int)v1;
}

```

## disassembly

```asm
0x18000c0cc  push    rbx
0x18000c0ce  sub     rsp, 30h
0x18000c0d2  mov     rax, [rcx]
0x18000c0d5  mov     rbx, rcx
0x18000c0d8  cmp     byte ptr [rax], 0
0x18000c0db  jz      short loc_18000C14D
0x18000c0dd  mov     rcx, [rcx+8]
0x18000c0e1  mov     rcx, [rcx]; Process
0x18000c0e4  call    cs:__imp_GetProcessId
0x18000c0ea  mov     edx, cs:dword_18003B0F8
0x18000c0f0  cmp     edx, 3
0x18000c0f3  jbe     short loc_18000C14D
0x18000c0f5  mov     rdx, cs:qword_18003B110
0x18000c0fc  mov     r8, 400000000000h
0x18000c106  mov     rcx, cs:qword_18003B108
0x18000c10d  test    r8, rcx
0x18000c110  jz      short loc_18000C14D
0x18000c112  mov     rcx, rdx
0x18000c115  and     rcx, r8
0x18000c118  cmp     rcx, rdx
0x18000c11b  jnz     short loc_18000C14D
0x18000c11d  mov     [rsp+38h+arg_0], eax
0x18000c121  lea     rdx, byte_1800357A9
0x18000c128  mov     rax, [rbx+10h]
0x18000c12c  mov     rcx, [rax]
0x18000c12f  lea     rax, [rsp+38h+arg_0]
0x18000c134  mov     [rsp+38h+var_10], rax
0x18000c139  lea     rax, [rsp+38h+arg_8]
0x18000c13e  mov     [rsp+38h+var_18], rax
0x18000c143  mov     [rsp+38h+arg_8], rcx
0x18000c148  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000c14d  add     rsp, 30h
0x18000c151  pop     rbx
0x18000c152  retn
```
