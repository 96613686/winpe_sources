# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)

- ea: `0x180001008`
- end: `0x1800010f2`
- name: `??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, __int64, const unsigned __int16 **)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000fa00`
- `0x180014a80`
- `0x180014d40`
- `0x18001506c`
- `0x180022d74`
- `0x180025bbc`
- `0x18002718c`
- `0x18002c744`

## callees

- `0x180001008`
- `0x18001bbe0`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1800010d7`
- `ntdll!EtwEventWriteTransfer` at `0x1800010d7`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5)
{
  const unsigned __int16 *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  _DWORD v9[2]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v10; // [rsp+40h] [rbp-40h]
  __int16 *v11; // [rsp+48h] [rbp-38h] BYREF
  int v12; // [rsp+50h] [rbp-30h]
  int v13; // [rsp+54h] [rbp-2Ch]
  unsigned __int8 *v14; // [rsp+58h] [rbp-28h]
  int v15; // [rsp+60h] [rbp-20h]
  int v16; // [rsp+64h] [rbp-1Ch]
  const unsigned __int16 *v17; // [rsp+68h] [rbp-18h]
  int v18; // [rsp+70h] [rbp-10h]
  int v19; // [rsp+74h] [rbp-Ch]

  v5 = *a5;
  if ( *a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *((_BYTE *)v5 + v6) );
    v7 = v6 + 1;
  }
  else
  {
    v5 = &word_1800359BA;
    v7 = 1;
  }
  v18 = v7;
  v9[0] = *a2 << 24;
  v9[1] = *(unsigned __int16 *)(a2 + 1);
  v10 = *(_QWORD *)(a2 + 3);
  v11 = (__int16 *)off_1800411B0;
  v17 = v5;
  v19 = 0;
  v12 = *(unsigned __int16 *)off_1800411B0;
  v15 = *(unsigned __int16 *)(a2 + 11);
  v14 = a2 + 11;
  v16 = 1;
  v13 = 2;
  return EtwEventWriteTransfer(qword_1800411C8, v9, 0, 0, 3, &v11);
}

```

## disassembly

```asm
0x180001008  push    rbp
0x18000100a  mov     rbp, rsp
0x18000100d  sub     rsp, 80h
0x180001014  mov     rax, cs:__security_cookie
0x18000101b  xor     rax, rsp
0x18000101e  mov     [rbp+var_8], rax
0x180001022  mov     rax, [rbp+arg_20]
0x180001026  mov     r8d, 1
0x18000102c  mov     rcx, [rax]
0x18000102f  test    rcx, rcx
0x180001032  jz      short loc_180001045
0x180001034  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001038  inc     rax
0x18000103b  cmp     byte ptr [rcx+rax], 0
0x18000103f  jnz     short loc_180001038
0x180001041  inc     eax
0x180001043  jmp     short loc_18000104F
0x180001045  lea     rcx, word_1800359BA
0x18000104c  mov     eax, r8d
0x18000104f  mov     [rbp+var_10], eax
0x180001052  xor     r9d, r9d
0x180001055  movzx   eax, byte ptr [rdx]
0x180001058  shl     eax, 18h
0x18000105b  mov     [rbp+var_48], eax
0x18000105e  movzx   eax, word ptr [rdx+1]
0x180001062  mov     [rbp+var_44], eax
0x180001065  mov     rax, [rdx+3]
0x180001069  mov     [rbp+var_40], rax
0x18000106d  mov     rax, cs:off_1800411B0
0x180001074  mov     [rbp+var_38], rax
0x180001078  mov     [rbp+var_18], rcx
0x18000107c  lea     rcx, [rdx+0Bh]
0x180001080  mov     [rbp+var_C], 0
0x180001087  lea     rdx, [rbp+var_48]
0x18000108b  movzx   eax, word ptr [rax]
0x18000108e  mov     [rbp+var_30], eax
0x180001091  movzx   eax, word ptr [rcx]
0x180001094  mov     [rbp+var_20], eax
0x180001097  lea     rax, _TraceLoggingMetadataEnd
0x18000109e  mov     [rbp+var_28], rcx
0x1800010a2  lea     rcx, _TraceLoggingMetadata
0x1800010a9  sub     eax, ecx
0x1800010ab  mov     [rbp+var_1C], r8d
0x1800010af  mov     [rbp+var_2C], 2
0x1800010b6  xor     r8d, r8d
0x1800010b9  mov     [rbp+var_50], eax
0x1800010bc  mov     eax, [rbp+var_50]
0x1800010bf  mov     rcx, cs:qword_1800411C8
0x1800010c6  lea     rax, [rbp+var_38]
0x1800010ca  mov     [rsp+80h+var_58], rax
0x1800010cf  mov     [rsp+80h+var_60], 3
0x1800010d7  call    cs:__imp_EtwEventWriteTransfer
0x1800010dd  mov     rcx, [rbp+var_8]
0x1800010e1  xor     rcx, rsp; StackCookie
0x1800010e4  call    __security_check_cookie
0x1800010e9  add     rsp, 80h
0x1800010f0  pop     rbp
0x1800010f1  retn
```
