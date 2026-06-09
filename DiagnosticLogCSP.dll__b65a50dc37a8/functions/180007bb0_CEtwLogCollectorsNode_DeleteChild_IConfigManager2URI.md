# CEtwLogCollectorsNode::DeleteChild(IConfigManager2URI *)

- ea: `0x180007bb0`
- end: `0x180007cee`
- name: `?DeleteChild@CEtwLogCollectorsNode@@UEAAJPEAUIConfigManager2URI@@@Z`
- size: `318`
- prototype: `__int64 __fastcall(CEtwLogCollectorsNode *__hidden this, struct IConfigManager2URI *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001090`
- `0x180007bb0`
- `0x1800092f8`
- `0x18000e744`
- `0x18000f228`
- `0x18000f3d0`
- `0x180039010`

## pseudocode

```c
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
      v6 = CEtwLogCollector::Open((HKEY *)&v10, v12, a3, a4);
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
      CFileDownload_DMChannel::~CFileDownload_DMChannel((CFileDownload_DMChannel *)&v10);
    }
  }
  else
  {
    v6 = -2046820335;
  }
LABEL_14:
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    LODWORD(v13) = *v4;
    LODWORD(v12) = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (unsigned __int8 *)&word_18004083E,
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
0x180007bb0  mov     [rsp-18h+arg_0], rbx
0x180007bb5  push    rbp
0x180007bb6  push    rsi
0x180007bb7  push    rdi
0x180007bb8  mov     rbp, rsp
0x180007bbb  sub     rsp, 50h
0x180007bbf  lea     rbx, [rcx+2Ch]
0x180007bc3  mov     rsi, rdx
0x180007bc6  test    rdx, rdx
0x180007bc9  jnz     short loc_180007BD5
0x180007bcb  mov     edi, 80070057h
0x180007bd0  jmp     loc_180007CAD
0x180007bd5  cmp     dword ptr [rbx], 2
0x180007bd8  jz      loc_180007C7F
0x180007bde  cmp     dword ptr [rbx], 8
0x180007be1  jz      short loc_180007BED
0x180007be3  mov     edi, 86000011h
0x180007be8  jmp     loc_180007CAD
0x180007bed  mov     rcx, [rcx+18h]
0x180007bf1  test    rcx, rcx
0x180007bf4  jz      short loc_180007BCB
0x180007bf6  mov     [rbp+arg_8], 0
0x180007bfe  lea     r8, [rbp+arg_8]
0x180007c02  mov     rax, [rcx]
0x180007c05  mov     edx, 3
0x180007c0a  mov     rax, [rax+58h]
0x180007c0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c13  mov     edi, eax
0x180007c15  test    eax, eax
0x180007c17  js      loc_180007CAD
0x180007c1d  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x180007c21  lea     rcx, [rbp+var_20]; this
0x180007c25  xorps   xmm0, xmm0
0x180007c28  mov     [rbp+var_10], 0
0x180007c30  movdqu  [rbp+var_20], xmm0
0x180007c35  call    ?Open@CEtwLogCollector@@QEAAJPEBG@Z; CEtwLogCollector::Open(ushort const *)
0x180007c3a  mov     edi, eax
0x180007c3c  test    eax, eax
0x180007c3e  jns     short loc_180007C4B
0x180007c40  lea     rcx, [rbp+var_20]; this
0x180007c44  call    ??1CFileDownload_DMChannel@@QEAA@XZ; CFileDownload_DMChannel::~CFileDownload_DMChannel(void)
0x180007c49  jmp     short loc_180007CAD
0x180007c4b  mov     rax, [rsi]
0x180007c4e  lea     r8, [rbp+arg_10]
0x180007c52  xor     edx, edx
0x180007c54  mov     [rbp+arg_10], 0
0x180007c5c  mov     rcx, rsi
0x180007c5f  mov     rax, [rax+58h]
0x180007c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c68  lea     rcx, [rbp+var_20]; this
0x180007c6c  mov     edi, eax
0x180007c6e  test    eax, eax
0x180007c70  js      short loc_180007C44
0x180007c72  mov     rdx, [rbp+arg_10]; unsigned __int16 *
0x180007c76  call    ?UnregisterProvider@CEtwLogCollector@@QEAAJPEBG@Z; CEtwLogCollector::UnregisterProvider(ushort const *)
0x180007c7b  mov     edi, eax
0x180007c7d  jmp     short loc_180007C40
0x180007c7f  mov     rax, [rdx]
0x180007c82  lea     r8, [rbp+arg_8]
0x180007c86  xor     edx, edx
0x180007c88  mov     [rbp+arg_8], 0
0x180007c90  mov     rcx, rsi
0x180007c93  mov     rax, [rax+58h]
0x180007c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c9c  mov     edi, eax
0x180007c9e  test    eax, eax
0x180007ca0  js      short loc_180007CAD
0x180007ca2  mov     rcx, [rbp+arg_8]; unsigned __int16 *
0x180007ca6  call    ?UnregisterCollector@CEtwLogCollector@@SAJPEBG@Z; CEtwLogCollector::UnregisterCollector(ushort const *)
0x180007cab  mov     edi, eax
0x180007cad  mov     eax, cs:dword_18004AE90
0x180007cb3  cmp     eax, 5
0x180007cb6  jbe     short loc_180007CDE
0x180007cb8  mov     eax, [rbx]
0x180007cba  lea     rdx, word_18004083E
0x180007cc1  mov     dword ptr [rbp+arg_10], eax
0x180007cc4  lea     rax, [rbp+arg_8]
0x180007cc8  mov     [rsp+50h+var_28], rax
0x180007ccd  lea     rax, [rbp+arg_10]
0x180007cd1  mov     [rsp+50h+var_30], rax
0x180007cd6  mov     dword ptr [rbp+arg_8], edi
0x180007cd9  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180007cde  mov     rbx, [rsp+50h+arg_0]
0x180007ce3  mov     eax, edi
0x180007ce5  add     rsp, 50h
0x180007ce9  pop     rdi
0x180007cea  pop     rsi
0x180007ceb  pop     rbp
0x180007cec  retn
```
