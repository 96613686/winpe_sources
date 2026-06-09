# CEtwLogCollectorsNode::DeleteChild(IConfigManager2URI *)

- ea: `0x180007a30`
- end: `0x180007b6d`
- name: `?DeleteChild@CEtwLogCollectorsNode@@UEAAJPEAUIConfigManager2URI@@@Z`
- size: `317`
- prototype: `__int64 __fastcall(CEtwLogCollectorsNode *this, struct IConfigManager2URI *, __int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000108c`
- `0x180007a30`
- `0x1800090b4`
- `0x18000e054`
- `0x18000eaf8`
- `0x18000ec90`
- `0x180037010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEtwLogCollectorsNode::DeleteChild(
        CEtwLogCollectorsNode *this,
        struct IConfigManager2URI *a2,
        __int64 a3,
        __int64 a4)
{
  _DWORD *v4; // rbx
  int v6; // edi
  __int64 v7; // rax
  __int64 v8; // rax
  __int128 v10; // [rsp+30h] [rbp-20h] BYREF
  __int64 v11; // [rsp+40h] [rbp-10h]
  unsigned __int16 *v12; // [rsp+78h] [rbp+28h] BYREF
  unsigned __int16 *v13; // [rsp+80h] [rbp+30h] BYREF

  v4 = (_DWORD *)((char *)this + 44);
  if ( !a2 )
    goto LABEL_2;
  if ( *v4 == 2 )
  {
    v8 = *(_QWORD *)a2;
    v12 = 0;
    v6 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, unsigned __int16 **))(v8 + 88))(a2, 0, &v12);
    if ( v6 >= 0 )
      v6 = CEtwLogCollector::UnregisterCollector(v12);
  }
  else if ( *v4 == 8 )
  {
    this = (CEtwLogCollectorsNode *)*((_QWORD *)this + 3);
    if ( !this )
    {
LABEL_2:
      v6 = -2147024809;
      goto LABEL_14;
    }
    v12 = 0;
    v6 = (*(__int64 (__fastcall **)(CEtwLogCollectorsNode *, __int64, unsigned __int16 **))(*(_QWORD *)this + 88LL))(
           this,
           3,
           &v12);
    if ( v6 >= 0 )
    {
      v11 = 0;
      v10 = 0;
      v6 = CEtwLogCollector::Open((CEtwLogCollector *)&v10, v12);
      if ( v6 >= 0 )
      {
        v7 = *(_QWORD *)a2;
        v13 = 0;
        v6 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, unsigned __int16 **))(v7 + 88))(
               a2,
               0,
               &v13);
        if ( v6 >= 0 )
          v6 = CEtwLogCollector::UnregisterProvider((CEtwLogCollector *)&v10, v13);
      }
      CFileDownload_DMChannel::~CFileDownload_DMChannel((HKEY *)&v10);
    }
  }
  else
  {
    v6 = -2046820335;
  }
LABEL_14:
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    LODWORD(v13) = *v4;
    LODWORD(v12) = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (__int64)&word_18003E83E,
      a3,
      a4,
      (__int64)&v13,
      (__int64)&v12);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180007a30  mov     [rsp-18h+arg_0], rbx
0x180007a35  push    rbp
0x180007a36  push    rsi
0x180007a37  push    rdi
0x180007a38  mov     rbp, rsp
0x180007a3b  sub     rsp, 50h
0x180007a3f  lea     rbx, [rcx+2Ch]
0x180007a43  mov     rsi, rdx
0x180007a46  test    rdx, rdx
0x180007a49  jnz     short loc_180007A55
0x180007a4b  mov     edi, 80070057h
0x180007a50  jmp     loc_180007B2D
0x180007a55  cmp     dword ptr [rbx], 2
0x180007a58  jz      loc_180007AFF
0x180007a5e  cmp     dword ptr [rbx], 8
0x180007a61  jz      short loc_180007A6D
0x180007a63  mov     edi, 86000011h
0x180007a68  jmp     loc_180007B2D
0x180007a6d  mov     rcx, [rcx+18h]
0x180007a71  test    rcx, rcx
0x180007a74  jz      short loc_180007A4B
0x180007a76  mov     [rbp+arg_8], 0
0x180007a7e  lea     r8, [rbp+arg_8]
0x180007a82  mov     rax, [rcx]
0x180007a85  mov     edx, 3
0x180007a8a  mov     rax, [rax+58h]
0x180007a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a93  mov     edi, eax
0x180007a95  test    eax, eax
0x180007a97  js      loc_180007B2D
0x180007a9d  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x180007aa1  lea     rcx, [rbp+var_20]; this
0x180007aa5  xorps   xmm0, xmm0
0x180007aa8  mov     [rbp+var_10], 0
0x180007ab0  movdqu  [rbp+var_20], xmm0
0x180007ab5  call    ?Open@CEtwLogCollector@@QEAAJPEBG@Z; CEtwLogCollector::Open(ushort const *)
0x180007aba  mov     edi, eax
0x180007abc  test    eax, eax
0x180007abe  jns     short loc_180007ACB
0x180007ac0  lea     rcx, [rbp+var_20]; this
0x180007ac4  call    ??1CFileDownload_DMChannel@@QEAA@XZ; CFileDownload_DMChannel::~CFileDownload_DMChannel(void)
0x180007ac9  jmp     short loc_180007B2D
0x180007acb  mov     rax, [rsi]
0x180007ace  lea     r8, [rbp+arg_10]
0x180007ad2  xor     edx, edx
0x180007ad4  mov     [rbp+arg_10], 0
0x180007adc  mov     rcx, rsi
0x180007adf  mov     rax, [rax+58h]
0x180007ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ae8  lea     rcx, [rbp+var_20]; this
0x180007aec  mov     edi, eax
0x180007aee  test    eax, eax
0x180007af0  js      short loc_180007AC4
0x180007af2  mov     rdx, [rbp+arg_10]; unsigned __int16 *
0x180007af6  call    ?UnregisterProvider@CEtwLogCollector@@QEAAJPEBG@Z; CEtwLogCollector::UnregisterProvider(ushort const *)
0x180007afb  mov     edi, eax
0x180007afd  jmp     short loc_180007AC0
0x180007aff  mov     rax, [rdx]
0x180007b02  lea     r8, [rbp+arg_8]
0x180007b06  xor     edx, edx
0x180007b08  mov     [rbp+arg_8], 0
0x180007b10  mov     rcx, rsi
0x180007b13  mov     rax, [rax+58h]
0x180007b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b1c  mov     edi, eax
0x180007b1e  test    eax, eax
0x180007b20  js      short loc_180007B2D
0x180007b22  mov     rcx, [rbp+arg_8]; unsigned __int16 *
0x180007b26  call    ?UnregisterCollector@CEtwLogCollector@@SAJPEBG@Z; CEtwLogCollector::UnregisterCollector(ushort const *)
0x180007b2b  mov     edi, eax
0x180007b2d  mov     eax, cs:dword_180048E90
0x180007b33  cmp     eax, 5
0x180007b36  jbe     short loc_180007B5E
0x180007b38  mov     eax, [rbx]
0x180007b3a  lea     rdx, word_18003E83E
0x180007b41  mov     dword ptr [rbp+arg_10], eax
0x180007b44  lea     rax, [rbp+arg_8]
0x180007b48  mov     [rsp+50h+var_28], rax
0x180007b4d  lea     rax, [rbp+arg_10]
0x180007b51  mov     [rsp+50h+var_30], rax
0x180007b56  mov     dword ptr [rbp+arg_8], edi
0x180007b59  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180007b5e  mov     rbx, [rsp+50h+arg_0]
0x180007b63  mov     eax, edi
0x180007b65  add     rsp, 50h
0x180007b69  pop     rdi
0x180007b6a  pop     rsi
0x180007b6b  pop     rbp
0x180007b6c  retn
```
