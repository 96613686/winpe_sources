# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_GenerateIncomingToastActionXml(WindowsInternal::ApplicationModel::Calls::IncomingToastAction,uint const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x180013ec0`
- end: `0x180014209`
- name: `?_GenerateIncomingToastActionXml@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAAJW4IncomingToastAction@234@AEBIPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `841`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800011fc`
- `0x180001dc0`
- `0x1800021b4`
- `0x180004a0c`
- `0x180004d80`
- `0x180005a90`
- `0x180011e5c`
- `0x180011e68`
- `0x180013ec0`
- `0x1800165c4`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180014074`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180014074`

## string_xrefs

- `0x180014020`: `<action activationType="foreground" content="%s" arguments="%s" imageUri="file:///%s"/>`
- `0x18001402e`: `<action activationType="background" content="%s" arguments="%s" imageUri="file:///%s"/>`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_GenerateIncomingToastActionXml(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _WORD *v5; // rcx
  unsigned int v7; // esi
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // edi
  void *v12; // rcx
  __int64 v14; // rcx
  const wchar_t *v15; // rbx
  UINT v16; // edi
  __int64 v17; // r8
  bool v18; // zf
  __int64 v19; // r8
  __int64 v20; // r9
  WCHAR Buffer[4]; // [rsp+30h] [rbp-79h] BYREF
  void *Block[2]; // [rsp+38h] [rbp-71h] BYREF
  __int16 v23; // [rsp+48h] [rbp-61h] BYREF
  __int64 v24; // [rsp+4Ah] [rbp-5Fh]
  int v25; // [rsp+52h] [rbp-57h]
  __int16 v26; // [rsp+56h] [rbp-53h]
  void *v27[2]; // [rsp+58h] [rbp-51h] BYREF
  __int16 v28; // [rsp+68h] [rbp-41h] BYREF
  __int64 v29; // [rsp+6Ah] [rbp-3Fh]
  int v30; // [rsp+72h] [rbp-37h]
  __int16 v31; // [rsp+76h] [rbp-33h]
  void *v32[2]; // [rsp+78h] [rbp-31h] BYREF
  __int16 v33; // [rsp+88h] [rbp-21h] BYREF
  __int64 v34; // [rsp+8Ah] [rbp-1Fh]
  int v35; // [rsp+92h] [rbp-17h]
  __int16 v36; // [rsp+96h] [rbp-13h]
  struct _EVENT_DATA_DESCRIPTOR v37; // [rsp+98h] [rbp-11h] BYREF
  WCHAR *v38; // [rsp+B8h] [rbp+Fh]
  __int64 v39; // [rsp+C0h] [rbp+17h]

  v5 = *(_WORD **)a4;
  *(_QWORD *)(a4 + 8) = *(_QWORD *)a4;
  v7 = a2;
  *v5 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  Block[0] = &v23;
  Block[1] = &v23;
  v23 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, void **))(*(_QWORD *)a1 + 176LL))(a1, a2, a3, Block);
  v11 = v8;
  if ( v8 < 0 )
  {
    Log_HREvent_1((unsigned int)v8, 1, v10, 710);
    v12 = Block[0];
    if ( Block[0] == &v23 )
      return (unsigned int)v11;
LABEL_3:
    operator delete(v12);
    return (unsigned int)v11;
  }
  switch ( v7 )
  {
    case 0u:
      v16 = 10007;
      goto LABEL_23;
    case 1u:
      v16 = 10003;
      goto LABEL_21;
    case 2u:
      v16 = 10004;
      goto LABEL_23;
    case 3u:
      v16 = 10005;
LABEL_23:
      v15 = L"<action activationType=\"background\" content=\"%s\" arguments=\"%s\" imageUri=\"file:///%s\"/>";
      goto LABEL_24;
    case 4u:
      v16 = 10001;
      goto LABEL_21;
  }
  v14 = v7 - 5;
  if ( v7 == 5 )
  {
    v16 = 10002;
    goto LABEL_21;
  }
  if ( v7 == 6 )
  {
    v16 = 10008;
LABEL_21:
    v15 = L"<action activationType=\"foreground\" content=\"%s\" arguments=\"%s\" imageUri=\"file:///%s\"/>";
    goto LABEL_24;
  }
  v15 = 0;
  v16 = 0;
  if ( (unsigned int)dword_180025038 > 4 )
  {
    *(_DWORD *)Buffer = v7;
    v38 = Buffer;
    v39 = 4;
    tlgWriteTransfer_EventWriteTransfer((int)&dword_180025038, (int)&word_180020ABE, 0, 0, 3u, &v37);
  }
  Log_AssertionEvent_2(v14, v9, 757);
  MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_24:
  v29 = 0;
  v31 = 0;
  v30 = 0;
  v27[0] = &v28;
  v27[1] = &v28;
  v28 = 0;
  *(_QWORD *)Buffer = 0;
  if ( !LoadStringW(g_resourceDll, v16, Buffer, 0) )
  {
    Log_AssertionEvent_0();
    __int2c();
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v27,
                           *(_QWORD *)Buffer) )
  {
    v11 = -2147024882;
    Log_HREvent_1(2147942414LL, 0, v17, 763);
    if ( v27[0] != &v28 )
      operator delete(v27[0]);
    v12 = Block[0];
    v18 = Block[0] == &v23;
    goto LABEL_30;
  }
  v34 = 0;
  v36 = 0;
  v35 = 0;
  v32[0] = &v33;
  v32[1] = &v33;
  v33 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, void **))(*(_QWORD *)a1 + 152LL))(a1, v7, v32);
  if ( v11 < 0 )
  {
    v20 = 767;
LABEL_34:
    Log_HREvent_1((unsigned int)v11, 1, v19, v20);
    if ( v32[0] != &v33 )
      operator delete(v32[0]);
    if ( v27[0] != &v28 )
      operator delete(v27[0]);
    v12 = Block[0];
    v18 = Block[0] == &v23;
LABEL_30:
    if ( v18 )
      return (unsigned int)v11;
    goto LABEL_3;
  }
  v11 = tlx::append_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
          a4,
          v15,
          v27[0],
          Block[0],
          v32[0]);
  if ( v11 < 0 )
  {
    v20 = 774;
    goto LABEL_34;
  }
  if ( v32[0] != &v33 )
    operator delete(v32[0]);
  if ( v27[0] != &v28 )
    operator delete(v27[0]);
  if ( Block[0] != &v23 )
    operator delete(Block[0]);
  return 0;
}

```

## disassembly

```asm
0x180013ec0  push    rbp
0x180013ec2  push    rbx
0x180013ec3  push    rsi
0x180013ec4  push    rdi
0x180013ec5  push    r14
0x180013ec7  push    r15
0x180013ec9  lea     rbp, [rsp-2Fh]
0x180013ece  sub     rsp, 0D8h
0x180013ed5  mov     rax, cs:__security_cookie
0x180013edc  xor     rax, rsp
0x180013edf  mov     [rbp+57h+var_38], rax
0x180013ee3  xor     eax, eax
0x180013ee5  mov     r14, rcx
0x180013ee8  mov     rcx, [r9]
0x180013eeb  mov     r15, r9
0x180013eee  mov     [r9+8], rcx
0x180013ef2  mov     esi, edx
0x180013ef4  lea     r9, [rbp+57h+Block]
0x180013ef8  mov     [rcx], ax
0x180013efb  mov     rcx, r14
0x180013efe  mov     [rbp+57h+var_B6], rax
0x180013f02  mov     [rbp+57h+var_AE], eax
0x180013f05  mov     [rbp+57h+var_AA], ax
0x180013f09  lea     rax, [rbp+57h+var_B8]
0x180013f0d  mov     [rbp+57h+Block], rax
0x180013f11  lea     rax, [rbp+57h+var_B8]
0x180013f15  mov     [rbp+57h+var_C0], rax
0x180013f19  xor     eax, eax
0x180013f1b  mov     [rbp+57h+var_B8], ax
0x180013f1f  mov     rax, [r14]
0x180013f22  mov     rax, [rax+0B0h]
0x180013f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f2e  mov     edi, eax
0x180013f30  test    eax, eax
0x180013f32  jns     short loc_180013F66
0x180013f34  mov     edx, 1
0x180013f39  mov     r9d, 2C6h
0x180013f3f  mov     ecx, eax
0x180013f41  call    Log_HREvent_1
0x180013f46  mov     rcx, [rbp+57h+Block]; Block
0x180013f4a  lea     rax, [rbp+57h+var_B8]
0x180013f4e  cmp     rcx, rax
0x180013f51  jz      short loc_180013F5F
0x180013f53  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180013f5a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013f5f  mov     eax, edi
0x180013f61  jmp     loc_1800141ED
0x180013f66  mov     ecx, esi
0x180013f68  test    esi, esi
0x180013f6a  jz      loc_180014029
0x180013f70  sub     ecx, 1
0x180013f73  jz      loc_18001401B
0x180013f79  sub     ecx, 1
0x180013f7c  jz      loc_180014014
0x180013f82  sub     ecx, 1
0x180013f85  jz      loc_18001400D
0x180013f8b  sub     ecx, 1
0x180013f8e  jz      short loc_180014006
0x180013f90  sub     ecx, 1
0x180013f93  jz      short loc_180013FFF
0x180013f95  cmp     ecx, 1
0x180013f98  jz      short loc_180013FF8
0x180013f9a  mov     eax, cs:dword_180025038
0x180013fa0  xor     ebx, ebx
0x180013fa2  xor     edi, edi
0x180013fa4  cmp     eax, 4
0x180013fa7  jbe     short loc_180013FE6
0x180013fa9  lea     rax, [rbp+57h+Buffer]
0x180013fad  mov     dword ptr [rbp+57h+Buffer], esi
0x180013fb0  mov     [rbp+57h+var_48], rax
0x180013fb4  lea     rdx, word_180020ABE; int
0x180013fbb  lea     rax, [rbp+57h+var_68]
0x180013fbf  mov     [rbp+57h+var_40], 4
0x180013fc7  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x180013fcc  lea     rcx, dword_180025038; int
0x180013fd3  xor     r9d, r9d; int
0x180013fd6  mov     [rsp+100h+var_E0], 3; ULONG
0x180013fde  xor     r8d, r8d; int
0x180013fe1  call    _tlgWriteTransfer_EventWriteTransfer
0x180013fe6  mov     r8d, 2F5h
0x180013fec  call    Log_AssertionEvent_2
0x180013ff1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180013ff6  jmp     short loc_180014035
0x180013ff8  mov     edi, 2718h
0x180013ffd  jmp     short loc_180014020
0x180013fff  mov     edi, 2712h
0x180014004  jmp     short loc_180014020
0x180014006  mov     edi, 2711h
0x18001400b  jmp     short loc_180014020
0x18001400d  mov     edi, 2715h
0x180014012  jmp     short loc_18001402E
0x180014014  mov     edi, 2714h
0x180014019  jmp     short loc_18001402E
0x18001401b  mov     edi, 2713h
0x180014020  lea     rbx, aActionActivati_0; "<action activationType=\"foreground\" c"...
0x180014027  jmp     short loc_180014035
0x180014029  mov     edi, 2717h
0x18001402e  lea     rbx, aActionActivati; "<action activationType=\"background\" c"...
0x180014035  mov     rcx, cs:?g_resourceDll@@3PEAUHINSTANCE__@@EA; hInstance
0x18001403c  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x180014040  xor     eax, eax
0x180014042  mov     [rbp+57h+var_96], 0
0x18001404a  mov     [rbp+57h+var_8A], ax
0x18001404e  xor     r9d, r9d; cchBufferMax
0x180014051  lea     rax, [rbp+57h+var_98]
0x180014055  mov     [rbp+57h+var_8E], 0
0x18001405c  mov     [rbp+57h+var_A8], rax
0x180014060  mov     edx, edi; uID
0x180014062  lea     rax, [rbp+57h+var_98]
0x180014066  mov     [rbp+57h+var_A0], rax
0x18001406a  xor     eax, eax
0x18001406c  mov     [rbp+57h+var_98], ax
0x180014070  mov     qword ptr [rbp+57h+Buffer], rax
0x180014074  call    cs:__imp_LoadStringW
0x18001407a  test    eax, eax
0x18001407c  jnz     short loc_180014085
0x18001407e  call    Log_AssertionEvent_0
0x180014083  int     2Ch; Windows NT - assertion failure
0x180014085  mov     rdx, qword ptr [rbp+57h+Buffer]
0x180014089  lea     rcx, [rbp+57h+var_A8]
0x18001408d  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180014092  test    al, al
0x180014094  jnz     short loc_1800140DF
0x180014096  mov     edi, 8007000Eh
0x18001409b  xor     edx, edx
0x18001409d  mov     ecx, edi
0x18001409f  mov     r9d, 2FBh
0x1800140a5  call    Log_HREvent_1
0x1800140aa  mov     rcx, [rbp+57h+var_A8]; Block
0x1800140ae  lea     rax, [rbp+57h+var_98]
0x1800140b2  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800140b9  cmp     rcx, rax
0x1800140bc  jz      short loc_1800140C6
0x1800140be  mov     rdx, rbx
0x1800140c1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800140c6  mov     rcx, [rbp+57h+Block]
0x1800140ca  lea     rdx, [rbp+57h+var_B8]
0x1800140ce  cmp     rcx, rdx
0x1800140d1  jz      loc_180013F5F
0x1800140d7  mov     rdx, rbx
0x1800140da  jmp     loc_180013F5A
0x1800140df  xor     eax, eax
0x1800140e1  mov     [rbp+57h+var_76], 0
0x1800140e9  mov     [rbp+57h+var_6A], ax
0x1800140ed  lea     r8, [rbp+57h+var_88]
0x1800140f1  lea     rax, [rbp+57h+var_78]
0x1800140f5  mov     [rbp+57h+var_6E], 0
0x1800140fc  mov     [rbp+57h+var_88], rax
0x180014100  mov     edx, esi
0x180014102  lea     rax, [rbp+57h+var_78]
0x180014106  mov     rcx, r14
0x180014109  mov     [rbp+57h+var_80], rax
0x18001410d  xor     eax, eax
0x18001410f  mov     [rbp+57h+var_78], ax
0x180014113  mov     rax, [r14]
0x180014116  mov     rax, [rax+98h]
0x18001411d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014122  mov     edi, eax
0x180014124  test    eax, eax
0x180014126  jns     short loc_18001417B
0x180014128  mov     r9d, 2FFh
0x18001412e  mov     edx, 1
0x180014133  mov     ecx, edi
0x180014135  call    Log_HREvent_1
0x18001413a  mov     rcx, [rbp+57h+var_88]; Block
0x18001413e  lea     rax, [rbp+57h+var_78]
0x180014142  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180014149  cmp     rcx, rax
0x18001414c  jz      short loc_180014156
0x18001414e  mov     rdx, rbx
0x180014151  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014156  mov     rcx, [rbp+57h+var_A8]; Block
0x18001415a  lea     rax, [rbp+57h+var_98]
0x18001415e  cmp     rcx, rax
0x180014161  jz      short loc_18001416B
0x180014163  mov     rdx, rbx
0x180014166  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001416b  mov     rcx, [rbp+57h+Block]
0x18001416f  lea     rax, [rbp+57h+var_B8]
0x180014173  cmp     rcx, rax
0x180014176  jmp     loc_1800140D1
0x18001417b  mov     rax, [rbp+57h+var_88]
0x18001417f  mov     rdx, rbx
0x180014182  mov     r9, [rbp+57h+Block]
0x180014186  mov     rcx, r15
0x180014189  mov     r8, [rbp+57h+var_A8]
0x18001418d  mov     qword ptr [rsp+100h+var_E0], rax
0x180014192  call    ??$append_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::append_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x180014197  mov     edi, eax
0x180014199  test    eax, eax
0x18001419b  jns     short loc_1800141A5
0x18001419d  mov     r9d, 306h
0x1800141a3  jmp     short loc_18001412E
0x1800141a5  mov     rcx, [rbp+57h+var_88]; Block
0x1800141a9  lea     rax, [rbp+57h+var_78]
0x1800141ad  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800141b4  cmp     rcx, rax
0x1800141b7  jz      short loc_1800141C1
0x1800141b9  mov     rdx, rbx
0x1800141bc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800141c1  mov     rcx, [rbp+57h+var_A8]; Block
0x1800141c5  lea     rax, [rbp+57h+var_98]
0x1800141c9  cmp     rcx, rax
0x1800141cc  jz      short loc_1800141D6
0x1800141ce  mov     rdx, rbx
0x1800141d1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800141d6  mov     rcx, [rbp+57h+Block]; Block
0x1800141da  lea     rax, [rbp+57h+var_B8]
0x1800141de  cmp     rcx, rax
0x1800141e1  jz      short loc_1800141EB
0x1800141e3  mov     rdx, rbx
0x1800141e6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800141eb  xor     eax, eax
0x1800141ed  mov     rcx, [rbp+57h+var_38]
0x1800141f1  xor     rcx, rsp; StackCookie
0x1800141f4  call    __security_check_cookie
0x1800141f9  add     rsp, 0D8h
0x180014200  pop     r15
0x180014202  pop     r14
0x180014204  pop     rdi
0x180014205  pop     rsi
0x180014206  pop     rbx
0x180014207  pop     rbp
0x180014208  retn
```
