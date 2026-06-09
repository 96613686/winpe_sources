# WriteDirScanFailureBuffer(DIRECTORY_SCAN_FUNC_ARGS *)

- ea: `0x180023944`
- end: `0x180023a9d`
- name: `?WriteDirScanFailureBuffer@@YAXPEAUDIRECTORY_SCAN_FUNC_ARGS@@@Z`
- size: `345`
- prototype: `void __fastcall(struct DIRECTORY_SCAN_FUNC_ARGS *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180022684`
- `0x180022ab4`

## callees

- `0x1800010b0`
- `0x180002c90`
- `0x180005c94`
- `0x180023944`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180023a17`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180023a17`

## pseudocode

```c
void __fastcall WriteDirScanFailureBuffer(struct DIRECTORY_SCAN_FUNC_ARGS *a1)
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

  if ( *((_WORD *)a1 + 352) )
  {
    if ( (unsigned int)dword_180040010 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180040010, 0x400000000000LL) )
      {
        v7 = v3;
        v12 = (unsigned __int16 *)((char *)a1 + 712);
        v6 = *((_QWORD *)a1 + 93);
        v8 = *((_QWORD *)a1 + 92);
        v10 = *((_QWORD *)a1 + 91);
        v9 = v3;
        v11 = v3;
        v13 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperArray<4>,_tlgWrapperArray<4>,_tlgWrapperArray<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
          v2,
          (__int64)word_180038412,
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
    v5 = (void *)*((_QWORD *)a1 + 91);
    *((_WORD *)a1 + 352) = 0;
    memset_0(v5, 0, 0xFA0u);
    memset_0(*((void **)a1 + 92), 0, 0xFA0u);
    memset_0(*((void **)a1 + 91), 0, 0xFA0u);
    memset_0(*((void **)a1 + 93), 0, 0xFA0u);
    memset_0(*((void **)a1 + 90), 0, *((unsigned __int16 *)a1 + 357));
    *((_WORD *)a1 + 356) = 0;
  }
}

```

## disassembly

```asm
0x180023944  mov     [rsp-18h+arg_10], rbx
0x180023949  push    rbp
0x18002394a  push    rsi
0x18002394b  push    rdi
0x18002394c  mov     rbp, rsp
0x18002394f  sub     rsp, 80h
0x180023956  movzx   r8d, word ptr [rcx+2C0h]
0x18002395e  xor     esi, esi
0x180023960  mov     rbx, rcx
0x180023963  test    r8w, r8w
0x180023967  jz      loc_180023A8A
0x18002396d  mov     eax, cs:dword_180040010
0x180023973  cmp     eax, 5
0x180023976  jbe     loc_180023A12
0x18002397c  mov     rdx, 400000000000h
0x180023986  lea     rcx, dword_180040010
0x18002398d  call    _tlgKeywordOn
0x180023992  test    al, al
0x180023994  jz      short loc_180023A12
0x180023996  lea     rax, [rbx+2C8h]
0x18002399d  mov     [rbp+var_28], r8w
0x1800239a2  mov     [rbp+arg_0], rax
0x1800239a6  lea     rdx, word_180038412
0x1800239ad  mov     rax, [rbx+2E8h]
0x1800239b4  mov     [rbp+var_30], rax
0x1800239b8  mov     rax, [rbx+2E0h]
0x1800239bf  mov     [rbp+var_20], rax
0x1800239c3  mov     rax, [rbx+2D8h]
0x1800239ca  mov     [rbp+var_10], rax
0x1800239ce  lea     rax, [rbp+arg_0]
0x1800239d2  mov     [rsp+80h+var_40], rax
0x1800239d7  lea     rax, [rbp+var_30]
0x1800239db  mov     [rsp+80h+var_48], rax
0x1800239e0  lea     rax, [rbp+var_20]
0x1800239e4  mov     [rsp+80h+var_50], rax
0x1800239e9  lea     rax, [rbp+var_10]
0x1800239ed  mov     [rsp+80h+var_58], rax
0x1800239f2  lea     rax, [rbp+arg_8]
0x1800239f6  mov     [rsp+80h+var_60], rax
0x1800239fb  mov     [rbp+var_18], r8w
0x180023a00  mov     [rbp+var_8], r8w
0x180023a05  mov     [rbp+arg_8], 1000000h
0x180023a0d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperArray@$03@@U2@U2@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperArray@$03@@44AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperArray<4>,_tlgWrapperArray<4>,_tlgWrapperArray<4>,_tlgWrapBuffer<_UNICODE_STRING>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperArray<4> const &,_tlgWrapperArray<4> const &,_tlgWrapperArray<4> const &,_tlgWrapBuffer<_UNICODE_STRING> const &)
0x180023a12  mov     ecx, 28h ; '('; dwMilliseconds
0x180023a17  call    cs:__imp_Sleep
0x180023a1d  mov     rcx, [rbx+2D8h]; void *
0x180023a24  mov     edi, 0FA0h
0x180023a29  mov     r8d, edi; Size
0x180023a2c  mov     [rbx+2C0h], si
0x180023a33  xor     edx, edx; Val
0x180023a35  call    memset_0
0x180023a3a  mov     rcx, [rbx+2E0h]; void *
0x180023a41  mov     r8d, edi; Size
0x180023a44  xor     edx, edx; Val
0x180023a46  call    memset_0
0x180023a4b  mov     rcx, [rbx+2D8h]; void *
0x180023a52  mov     r8d, edi; Size
0x180023a55  xor     edx, edx; Val
0x180023a57  call    memset_0
0x180023a5c  mov     rcx, [rbx+2E8h]; void *
0x180023a63  mov     r8d, edi; Size
0x180023a66  xor     edx, edx; Val
0x180023a68  call    memset_0
0x180023a6d  movzx   r8d, word ptr [rbx+2CAh]; Size
0x180023a75  xor     edx, edx; Val
0x180023a77  mov     rcx, [rbx+2D0h]; void *
0x180023a7e  call    memset_0
0x180023a83  mov     [rbx+2C8h], si
0x180023a8a  mov     rbx, [rsp+80h+arg_10]
0x180023a92  add     rsp, 80h
0x180023a99  pop     rdi
0x180023a9a  pop     rsi
0x180023a9b  pop     rbp
0x180023a9c  retn
```
