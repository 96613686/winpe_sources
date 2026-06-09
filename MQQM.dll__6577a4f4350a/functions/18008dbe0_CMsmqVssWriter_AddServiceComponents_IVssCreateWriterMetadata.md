# CMsmqVssWriter::AddServiceComponents(IVssCreateWriterMetadata *)

- ea: `0x18008dbe0`
- end: `0x18008dd7b`
- name: `?AddServiceComponents@CMsmqVssWriter@@AEAAJPEAVIVssCreateWriterMetadata@@@Z`
- size: `411`
- prototype: `__int64 __fastcall(CMsmqVssWriter *__hidden this, struct IVssCreateWriterMetadata *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180091460`

## callees

- `0x18002c61c`
- `0x18008dbe0`
- `0x18008dd84`
- `0x18008e528`
- `0x18009a590`
- `0x1800e4010`

## import_xrefs

- `msvcrt!free` at `0x18008dc6f`
- `msvcrt!free` at `0x18008dd07`
- `msvcrt!free` at `0x18008dd49`
- `msvcrt!free` at `0x18008dd5d`
- `msvcrt!free` at `0x18008dc6f`
- `msvcrt!free` at `0x18008dd07`
- `msvcrt!free` at `0x18008dd49`
- `msvcrt!free` at `0x18008dd5d`

## string_xrefs

- `0x18008dc11`: `MsmqRootPath`
- `0x18008dc58`: `writer/mqwriter`
- `0x18008dcdc`: `writer/mqwriter`
- `0x18008dcf0`: `writer/mqwriter`
- `0x18008dd32`: `writer/mqwriter`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMsmqVssWriter::AddServiceComponents(CMsmqVssWriter *this, struct IVssCreateWriterMetadata *a2)
{
  int v4; // eax
  unsigned int v5; // edi
  int v7; // eax
  int v8; // eax
  char v9; // [rsp+38h] [rbp-70h]
  char v10; // [rsp+40h] [rbp-68h]
  char v11; // [rsp+48h] [rbp-60h]
  char v12; // [rsp+50h] [rbp-58h]
  int v13; // [rsp+70h] [rbp-38h] BYREF
  __int64 v14; // [rsp+78h] [rbp-30h]
  const wchar_t *v15; // [rsp+80h] [rbp-28h]
  int v16; // [rsp+88h] [rbp-20h]
  __int64 v17; // [rsp+90h] [rbp-18h]
  void *Block; // [rsp+B0h] [rbp+8h] BYREF

  Block = 0;
  v13 = 1;
  v14 = *((_QWORD *)this + 4);
  v15 = L"MsmqRootPath";
  v16 = 0;
  v17 = -2147483646;
  CmQueryValue((const struct RegEntry *)&v13, (wchar_t **)&Block);
  v4 = CMsmqVssWriter::AddServiceConfig(this, a2, (const wchar_t *)Block);
  v5 = v4;
  if ( v4 < 0 )
  {
    LogMsgHR(v4, (wchar_t *)L"writer/mqwriter", 0x4ECu);
    free(Block);
    return v5;
  }
  v12 = 1;
  v11 = 1;
  v10 = 0;
  v9 = 0;
  v7 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, __int64, _QWORD, const wchar_t *, _QWORD, _QWORD, _DWORD, char, char, char, char, _DWORD))(*(_QWORD *)a2 + 16LL))(
         a2,
         2,
         0,
         L"storage",
         0,
         0,
         0,
         v9,
         v10,
         v11,
         v12,
         0);
  v5 = v7;
  if ( v7 < 0 )
  {
    LogMsgHR(v7, (wchar_t *)L"writer/mqwriter", 0x3ACu);
    LogMsgHR(v5, (wchar_t *)L"writer/mqwriter", 0x514u);
    free(Block);
    return v5;
  }
  v8 = CMsmqVssWriter::AddServiceQueues(this, a2, (const wchar_t *)Block);
  v5 = v8;
  if ( v8 < 0 )
  {
    LogMsgHR(v8, (wchar_t *)L"writer/mqwriter", 0x500u);
    free(Block);
    return v5;
  }
  free(Block);
  return 0;
}

```

## disassembly

```asm
0x18008dbe0  mov     r11, rsp
0x18008dbe3  mov     [r11+10h], rbp
0x18008dbe7  mov     [r11+18h], rsi
0x18008dbeb  push    rdi
0x18008dbec  sub     rsp, 0A0h
0x18008dbf3  mov     rsi, rdx
0x18008dbf6  mov     rbp, rcx
0x18008dbf9  mov     qword ptr [r11+8], 0
0x18008dc01  mov     [rsp+0A8h+var_38], 1
0x18008dc09  mov     rax, [rcx+20h]
0x18008dc0d  mov     [r11-30h], rax
0x18008dc11  lea     rax, aMsmqrootpath; "MsmqRootPath"
0x18008dc18  mov     [r11-28h], rax
0x18008dc1c  mov     dword ptr [r11-20h], 0
0x18008dc24  mov     qword ptr [r11-18h], 0FFFFFFFF80000002h
0x18008dc2c  lea     rdx, [r11+8]; wchar_t **
0x18008dc30  lea     rcx, [r11-38h]; struct RegEntry *
0x18008dc34  call    ?CmQueryValue@@YAXAEBVRegEntry@@PEAPEA_W@Z; CmQueryValue(RegEntry const &,wchar_t * *)
0x18008dc39  mov     r8, [rsp+0A8h+Block]; wchar_t *
0x18008dc41  mov     rdx, rsi; struct IVssCreateWriterMetadata *
0x18008dc44  mov     rcx, rbp; this
0x18008dc47  call    ?AddServiceConfig@CMsmqVssWriter@@AEAAJPEAVIVssCreateWriterMetadata@@PEB_W@Z; CMsmqVssWriter::AddServiceConfig(IVssCreateWriterMetadata *,wchar_t const *)
0x18008dc4c  mov     edi, eax
0x18008dc4e  test    eax, eax
0x18008dc50  jns     short loc_18008DC7D
0x18008dc52  mov     r8d, 4ECh; unsigned __int16
0x18008dc58  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008dc5f  mov     ecx, eax; int
0x18008dc61  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008dc66  nop
0x18008dc67  mov     rcx, [rsp+0A8h+Block]; Block
0x18008dc6f  call    cs:__imp_free
0x18008dc75  nop
0x18008dc76  mov     eax, edi
0x18008dc78  jmp     loc_18008DD66
0x18008dc7d  mov     rax, [rsi]
0x18008dc80  mov     [rsp+0A8h+var_50], 0
0x18008dc88  mov     [rsp+0A8h+var_58], 1
0x18008dc8d  mov     [rsp+0A8h+var_60], 1
0x18008dc92  mov     [rsp+0A8h+var_68], 0
0x18008dc97  mov     [rsp+0A8h+var_70], 0
0x18008dc9c  mov     [rsp+0A8h+var_78], 0
0x18008dca4  mov     [rsp+0A8h+var_80], 0
0x18008dcad  mov     [rsp+0A8h+var_88], 0
0x18008dcb6  lea     r9, aStorage; "storage"
0x18008dcbd  xor     r8d, r8d
0x18008dcc0  lea     edx, [r8+2]
0x18008dcc4  mov     rcx, rsi
0x18008dcc7  mov     rax, [rax+10h]
0x18008dccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dcd0  mov     edi, eax
0x18008dcd2  test    eax, eax
0x18008dcd4  jns     short loc_18008DD13
0x18008dcd6  mov     r8d, 3ACh; unsigned __int16
0x18008dcdc  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008dce3  mov     ecx, eax; int
0x18008dce5  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008dcea  mov     r8d, 514h; unsigned __int16
0x18008dcf0  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008dcf7  mov     ecx, edi; int
0x18008dcf9  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008dcfe  nop
0x18008dcff  mov     rcx, [rsp+0A8h+Block]; Block
0x18008dd07  call    cs:__imp_free
0x18008dd0d  nop
0x18008dd0e  jmp     loc_18008DC76
0x18008dd13  mov     r8, [rsp+0A8h+Block]; wchar_t *
0x18008dd1b  mov     rdx, rsi; struct IVssCreateWriterMetadata *
0x18008dd1e  mov     rcx, rbp; this
0x18008dd21  call    ?AddServiceQueues@CMsmqVssWriter@@AEAAJPEAVIVssCreateWriterMetadata@@PEB_W@Z; CMsmqVssWriter::AddServiceQueues(IVssCreateWriterMetadata *,wchar_t const *)
0x18008dd26  mov     edi, eax
0x18008dd28  test    eax, eax
0x18008dd2a  jns     short loc_18008DD55
0x18008dd2c  mov     r8d, 500h; unsigned __int16
0x18008dd32  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008dd39  mov     ecx, eax; int
0x18008dd3b  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008dd40  nop
0x18008dd41  mov     rcx, [rsp+0A8h+Block]; Block
0x18008dd49  call    cs:__imp_free
0x18008dd4f  nop
0x18008dd50  jmp     loc_18008DC76
0x18008dd55  mov     rcx, [rsp+0A8h+Block]; Block
0x18008dd5d  call    cs:__imp_free
0x18008dd63  nop
0x18008dd64  xor     eax, eax
0x18008dd66  lea     r11, [rsp+0A8h+var_8]
0x18008dd6e  mov     rbp, [r11+18h]
0x18008dd72  mov     rsi, [r11+20h]
0x18008dd76  mov     rsp, r11
0x18008dd79  pop     rdi
0x18008dd7a  retn
```
