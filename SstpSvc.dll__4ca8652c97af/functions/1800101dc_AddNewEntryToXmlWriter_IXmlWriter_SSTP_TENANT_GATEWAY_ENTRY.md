# AddNewEntryToXmlWriter(IXmlWriter *,_SSTP_TENANT_GATEWAY_ENTRY *)

- ea: `0x1800101dc`
- end: `0x1800103e0`
- name: `?AddNewEntryToXmlWriter@@YAKPEAUIXmlWriter@@PEAU_SSTP_TENANT_GATEWAY_ENTRY@@@Z`
- size: `516`
- prototype: `__int64 __fastcall(struct IXmlWriter *, struct _SSTP_TENANT_GATEWAY_ENTRY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800138c0`

## callees

- `0x18000827c`
- `0x180008360`
- `0x1800101dc`
- `0x18001bcba`
- `0x18001bcf0`
- `0x18001d010`

## string_xrefs

- `0x18001036e`: `AddNewEntryToXmlWriter: WriteStartElement of IXmlWriter object failed with error %d`
- `0x180010293`: `AddNewEntryToXmlWriter: WriteString of IXmlWriter object failed with error %d`
- `0x1800102ce`: `AddNewEntryToXmlWriter: WriteFullEndElement of IXmlWriter object failed with error %d`

## pseudocode

```c
__int64 __fastcall AddNewEntryToXmlWriter(struct IXmlWriter *a1, struct _SSTP_TENANT_GATEWAY_ENTRY *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // r8
  unsigned int i; // esi
  __int64 result; // rax
  int v9; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v10[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  v4 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const wchar_t *, _QWORD))a1->lpVtbl->WriteStartElement)(
         a1,
         0,
         L"Tenant",
         0);
  v5 = v4;
  if ( v4 )
  {
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_21;
    v6 = v4;
    LOWORD(v9) = 0;
LABEL_18:
    FormatRRASErrorString(
      &v9,
      L"AddNewEntryToXmlWriter: WriteStartElement of IXmlWriter object failed with error %d",
      v6);
LABEL_19:
    if ( (byte_18002D803 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v9);
    goto LABEL_21;
  }
  v5 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD))a1->lpVtbl->WriteString)(a1, *((_QWORD *)a2 + 1));
  if ( v5 )
  {
LABEL_5:
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_21;
    LOWORD(v9) = 0;
    FormatRRASErrorString(&v9, L"AddNewEntryToXmlWriter: WriteString of IXmlWriter object failed with error %d", v5);
    goto LABEL_19;
  }
  v5 = ((__int64 (__fastcall *)(struct IXmlWriter *))a1->lpVtbl->WriteFullEndElement)(a1);
  if ( v5 )
  {
LABEL_8:
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_21;
    LOWORD(v9) = 0;
    FormatRRASErrorString(
      &v9,
      L"AddNewEntryToXmlWriter: WriteFullEndElement of IXmlWriter object failed with error %d",
      v5);
    goto LABEL_19;
  }
  for ( i = 0; i < *((_DWORD *)a2 + 4); ++i )
  {
    v5 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const wchar_t *, _QWORD))a1->lpVtbl->WriteStartElement)(
           a1,
           0,
           L"Gateway",
           0);
    if ( v5 )
    {
      if ( (byte_18002D803 & 8) == 0 )
        break;
      v6 = v5;
      LOWORD(v9) = 0;
      goto LABEL_18;
    }
    v5 = ((__int64 (__fastcall *)(struct IXmlWriter *, __int64))a1->lpVtbl->WriteString)(
           a1,
           *((_QWORD *)a2 + 3) + 510LL * i);
    if ( v5 )
      goto LABEL_5;
    v5 = ((__int64 (__fastcall *)(struct IXmlWriter *))a1->lpVtbl->WriteFullEndElement)(a1);
    if ( v5 )
      goto LABEL_8;
  }
LABEL_21:
  result = 0;
  if ( (v5 & 0x80000000) != 0 )
  {
    result = (unsigned __int16)v5;
    if ( (v5 & 0x1FFF0000) != 0x70000 )
      return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800101dc  mov     [rsp-8+arg_10], rbx
0x1800101e1  mov     [rsp-8+arg_18], rsi
0x1800101e6  push    rbp
0x1800101e7  push    rdi
0x1800101e8  push    r14
0x1800101ea  lea     rbp, [rsp-740h]
0x1800101f2  sub     rsp, 840h
0x1800101f9  mov     rax, cs:__security_cookie
0x180010200  xor     rax, rsp
0x180010203  mov     [rbp+750h+var_20], rax
0x18001020a  mov     r14, rdx
0x18001020d  mov     rdi, rcx
0x180010210  xor     eax, eax
0x180010212  lea     rcx, [rsp+850h+var_81C]; void *
0x180010217  xor     edx, edx; Val
0x180010219  mov     [rsp+850h+var_820], eax
0x18001021d  mov     r8d, 7FCh; Size
0x180010223  call    memset_0
0x180010228  mov     rax, [rdi]
0x18001022b  lea     r8, aTenant; "Tenant"
0x180010232  xor     r9d, r9d
0x180010235  xor     edx, edx
0x180010237  mov     rcx, rdi
0x18001023a  mov     rax, [rax+0D8h]
0x180010241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010246  mov     ebx, eax
0x180010248  test    eax, eax
0x18001024a  jz      short loc_180010268
0x18001024c  test    cs:byte_18002D803, 8
0x180010253  jz      loc_1800103A0
0x180010259  xor     ecx, ecx
0x18001025b  mov     r8d, eax
0x18001025e  mov     word ptr [rsp+850h+var_820], cx
0x180010263  jmp     loc_18001036E
0x180010268  mov     rax, [rdi]
0x18001026b  mov     rcx, rdi
0x18001026e  mov     rdx, [r14+8]
0x180010272  mov     rax, [rax+0E0h]
0x180010279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001027e  mov     ebx, eax
0x180010280  test    eax, eax
0x180010282  jz      short loc_1800102A7
0x180010284  test    cs:byte_18002D803, 8
0x18001028b  jz      loc_1800103A0
0x180010291  xor     eax, eax
0x180010293  lea     rdx, aAddnewentrytox_1; "AddNewEntryToXmlWriter: WriteString of "...
0x18001029a  mov     word ptr [rsp+850h+var_820], ax
0x18001029f  mov     r8d, ebx
0x1800102a2  jmp     loc_180010375
0x1800102a7  mov     rax, [rdi]
0x1800102aa  mov     rcx, rdi
0x1800102ad  mov     rax, [rax+88h]
0x1800102b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102b9  mov     ebx, eax
0x1800102bb  test    eax, eax
0x1800102bd  jz      short loc_1800102E2
0x1800102bf  test    cs:byte_18002D803, 8
0x1800102c6  jz      loc_1800103A0
0x1800102cc  xor     eax, eax
0x1800102ce  lea     rdx, aAddnewentrytox_0; "AddNewEntryToXmlWriter: WriteFullEndEle"...
0x1800102d5  mov     word ptr [rsp+850h+var_820], ax
0x1800102da  mov     r8d, ebx
0x1800102dd  jmp     loc_180010375
0x1800102e2  xor     esi, esi
0x1800102e4  cmp     esi, [r14+10h]
0x1800102e8  jnb     loc_1800103A0
0x1800102ee  mov     rax, [rdi]
0x1800102f1  lea     r8, aGateway; "Gateway"
0x1800102f8  xor     r9d, r9d
0x1800102fb  xor     edx, edx
0x1800102fd  mov     rcx, rdi
0x180010300  mov     rax, [rax+0D8h]
0x180010307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001030c  mov     ebx, eax
0x18001030e  test    eax, eax
0x180010310  jnz     short loc_18001035B
0x180010312  mov     rcx, [rdi]
0x180010315  mov     eax, esi
0x180010317  imul    rdx, rax, 1FEh
0x18001031e  mov     rax, [rcx+0E0h]
0x180010325  mov     rcx, rdi
0x180010328  add     rdx, [r14+18h]
0x18001032c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010331  mov     ebx, eax
0x180010333  test    eax, eax
0x180010335  jnz     loc_180010284
0x18001033b  mov     rax, [rdi]
0x18001033e  mov     rcx, rdi
0x180010341  mov     rax, [rax+88h]
0x180010348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001034d  mov     ebx, eax
0x18001034f  test    eax, eax
0x180010351  jnz     loc_1800102BF
0x180010357  inc     esi
0x180010359  jmp     short loc_1800102E4
0x18001035b  test    cs:byte_18002D803, 8
0x180010362  jz      short loc_1800103A0
0x180010364  xor     eax, eax
0x180010366  mov     r8d, ebx
0x180010369  mov     word ptr [rsp+850h+var_820], ax
0x18001036e  lea     rdx, aAddnewentrytox; "AddNewEntryToXmlWriter: WriteStartEleme"...
0x180010375  lea     rcx, [rsp+850h+var_820]
0x18001037a  call    FormatRRASErrorString
0x18001037f  test    cs:byte_18002D803, 8
0x180010386  jz      short loc_1800103A0
0x180010388  lea     r8, [rsp+850h+var_820]
0x18001038d  lea     rdx, RasSSTPSvcTraceError
0x180010394  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001039b  call    McTemplateU0z_EventWriteTransfer
0x1800103a0  xor     eax, eax
0x1800103a2  test    ebx, ebx
0x1800103a4  jns     short loc_1800103B9
0x1800103a6  mov     eax, ebx
0x1800103a8  and     eax, 1FFF0000h
0x1800103ad  cmp     eax, 70000h
0x1800103b2  movzx   eax, bx
0x1800103b5  jz      short loc_1800103B9
0x1800103b7  mov     eax, ebx
0x1800103b9  mov     rcx, [rbp+750h+var_20]
0x1800103c0  xor     rcx, rsp; StackCookie
0x1800103c3  call    __security_check_cookie
0x1800103c8  lea     r11, [rsp+850h+var_10]
0x1800103d0  mov     rbx, [r11+30h]
0x1800103d4  mov     rsi, [r11+38h]
0x1800103d8  mov     rsp, r11
0x1800103db  pop     r14
0x1800103dd  pop     rdi
0x1800103de  pop     rbp
0x1800103df  retn
```
