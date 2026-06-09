# WriteRegScanFailureBuffer(REGISTRY_SCAN_FUNC_ARGS *)

- ea: `0x180025388`
- end: `0x1800254ba`
- name: `?WriteRegScanFailureBuffer@@YAXPEAUREGISTRY_SCAN_FUNC_ARGS@@@Z`
- size: `306`
- prototype: `void __fastcall(struct REGISTRY_SCAN_FUNC_ARGS *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180024660`
- `0x180024938`

## callees

- `0x1800010b0`
- `0x180002c90`
- `0x180005c94`
- `0x180025388`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002544c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002544c`

## pseudocode

```c
void __fastcall WriteRegScanFailureBuffer(struct REGISTRY_SCAN_FUNC_ARGS *a1)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  void *v5; // rcx
  __int64 v6; // [rsp+50h] [rbp-30h] BYREF
  __int16 v7; // [rsp+58h] [rbp-28h]
  __int64 v8; // [rsp+60h] [rbp-20h] BYREF
  __int16 v9; // [rsp+68h] [rbp-18h]
  __int64 v10; // [rsp+70h] [rbp-10h] BYREF
  __int16 v11; // [rsp+78h] [rbp-8h]
  unsigned __int16 *v12; // [rsp+A0h] [rbp+20h] BYREF
  __int64 v13; // [rsp+A8h] [rbp+28h] BYREF

  if ( *((_WORD *)a1 + 24) )
  {
    if ( (unsigned int)dword_180040010 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180040010, 0x400000000000LL) )
      {
        v7 = v3;
        v12 = (unsigned __int16 *)((char *)a1 + 56);
        v6 = *((_QWORD *)a1 + 11);
        v8 = *((_QWORD *)a1 + 10);
        v10 = *((_QWORD *)a1 + 9);
        v9 = v3;
        v11 = v3;
        v13 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperArray<4>,_tlgWrapperArray<4>,_tlgWrapperArray<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
          v2,
          (__int64)byte_18003846D,
          v3,
          v4,
          (__int64)&v13,
          &v10,
          &v8,
          &v6,
          &v12);
      }
    }
    Sleep(0x28u);
    v5 = (void *)*((_QWORD *)a1 + 9);
    *((_WORD *)a1 + 24) = 0;
    memset_0(v5, 0, 0x320u);
    memset_0(*((void **)a1 + 10), 0, 0x320u);
    memset_0(*((void **)a1 + 9), 0, 0x320u);
    memset_0(*((void **)a1 + 11), 0, 0x320u);
    memset_0(*((void **)a1 + 8), 0, *((unsigned __int16 *)a1 + 29));
    *((_WORD *)a1 + 28) = 0;
  }
}

```

## disassembly

```asm
0x180025388  mov     [rsp-18h+arg_10], rbx
0x18002538d  push    rbp
0x18002538e  push    rsi
0x18002538f  push    rdi
0x180025390  mov     rbp, rsp
0x180025393  sub     rsp, 80h
0x18002539a  movzx   r8d, word ptr [rcx+30h]
0x18002539f  xor     esi, esi
0x1800253a1  mov     rbx, rcx
0x1800253a4  test    r8w, r8w
0x1800253a8  jz      loc_1800254A7
0x1800253ae  mov     eax, cs:dword_180040010
0x1800253b4  cmp     eax, 5
0x1800253b7  jbe     loc_180025447
0x1800253bd  mov     rdx, 400000000000h
0x1800253c7  lea     rcx, dword_180040010
0x1800253ce  call    _tlgKeywordOn
0x1800253d3  test    al, al
0x1800253d5  jz      short loc_180025447
0x1800253d7  lea     rax, [rbx+38h]
0x1800253db  mov     [rbp+var_28], r8w
0x1800253e0  mov     [rbp+arg_0], rax
0x1800253e4  lea     rdx, byte_18003846D
0x1800253eb  mov     rax, [rbx+58h]
0x1800253ef  mov     [rbp+var_30], rax
0x1800253f3  mov     rax, [rbx+50h]
0x1800253f7  mov     [rbp+var_20], rax
0x1800253fb  mov     rax, [rbx+48h]
0x1800253ff  mov     [rbp+var_10], rax
0x180025403  lea     rax, [rbp+arg_0]
0x180025407  mov     [rsp+80h+var_40], rax
0x18002540c  lea     rax, [rbp+var_30]
0x180025410  mov     [rsp+80h+var_48], rax
0x180025415  lea     rax, [rbp+var_20]
0x180025419  mov     [rsp+80h+var_50], rax
0x18002541e  lea     rax, [rbp+var_10]
0x180025422  mov     [rsp+80h+var_58], rax
0x180025427  lea     rax, [rbp+arg_8]
0x18002542b  mov     [rsp+80h+var_60], rax
0x180025430  mov     [rbp+var_18], r8w
0x180025435  mov     [rbp+var_8], r8w
0x18002543a  mov     [rbp+arg_8], 1000000h
0x180025442  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperArray@$03@@U2@U2@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperArray@$03@@44AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperArray<4>,_tlgWrapperArray<4>,_tlgWrapperArray<4>,_tlgWrapBuffer<_UNICODE_STRING>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperArray<4> const &,_tlgWrapperArray<4> const &,_tlgWrapperArray<4> const &,_tlgWrapBuffer<_UNICODE_STRING> const &)
0x180025447  mov     ecx, 28h ; '('; dwMilliseconds
0x18002544c  call    cs:__imp_Sleep
0x180025452  mov     rcx, [rbx+48h]; void *
0x180025456  mov     edi, 320h
0x18002545b  mov     r8d, edi; Size
0x18002545e  mov     [rbx+30h], si
0x180025462  xor     edx, edx; Val
0x180025464  call    memset_0
0x180025469  mov     rcx, [rbx+50h]; void *
0x18002546d  mov     r8d, edi; Size
0x180025470  xor     edx, edx; Val
0x180025472  call    memset_0
0x180025477  mov     rcx, [rbx+48h]; void *
0x18002547b  mov     r8d, edi; Size
0x18002547e  xor     edx, edx; Val
0x180025480  call    memset_0
0x180025485  mov     rcx, [rbx+58h]; void *
0x180025489  mov     r8d, edi; Size
0x18002548c  xor     edx, edx; Val
0x18002548e  call    memset_0
0x180025493  movzx   r8d, word ptr [rbx+3Ah]; Size
0x180025498  xor     edx, edx; Val
0x18002549a  mov     rcx, [rbx+40h]; void *
0x18002549e  call    memset_0
0x1800254a3  mov     [rbx+38h], si
0x1800254a7  mov     rbx, [rsp+80h+arg_10]
0x1800254af  add     rsp, 80h
0x1800254b6  pop     rdi
0x1800254b7  pop     rsi
0x1800254b8  pop     rbp
0x1800254b9  retn
```
