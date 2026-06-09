# CPartnershipStateManager::EnsureChangeTracker(ClientPartnershipDescriptor &,std::shared_ptr<void> &)

- ea: `0x180033520`
- end: `0x1800337e5`
- name: `?EnsureChangeTracker@CPartnershipStateManager@@UEAAXAEAVClientPartnershipDescriptor@@AEAV?$shared_ptr@X@std@@@Z`
- size: `709`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180030f44`

## callees

- `0x180002ab0`
- `0x180003604`
- `0x180007e10`
- `0x180010ee0`
- `0x180011314`
- `0x18001137c`
- `0x180033520`
- `0x180033a2c`
- `0x1800351d8`
- `0x180061e18`
- `0x18006604c`
- `0x18013e010`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x1800335fd`
- `KERNEL32!GetFileAttributesW` at `0x1800335fd`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180033659`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180033659`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CPartnershipStateManager::EnsureChangeTracker(__int64 a1, _QWORD *a2, __int64 a3)
{
  _BYTE *v6; // rax
  char v7; // cl
  __int64 v8; // rax
  const WCHAR *v9; // rax
  const unsigned __int16 *v10; // rax
  HRESULT v11; // eax
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // r11
  __int64 v15; // rax
  __int64 v16; // r10
  __int64 v17; // rax
  __int64 v18; // r10
  unsigned __int16 *v19; // rax
  __int64 v20; // rax
  __int64 v21; // r11
  __int64 v22; // rax
  int pExceptionObject; // [rsp+50h] [rbp-19h] BYREF
  int v24; // [rsp+58h] [rbp-11h] BYREF
  int v25; // [rsp+5Ch] [rbp-Dh]
  char v26; // [rsp+60h] [rbp-9h]
  const char *v27; // [rsp+68h] [rbp-1h]
  __int64 v28; // [rsp+70h] [rbp+7h]
  GUID pguid; // [rsp+78h] [rbp+Fh] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( (v6[68] & 8) == 0 || (v7 = 1, v6[65] < 6u) )
    v7 = 0;
  v24 = 0;
  v25 = 146;
  v26 = v7;
  v27 = "CPartnershipStateManager::EnsureChangeTracker";
  v28 = 0;
  v8 = a2[41] - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v8 )
    v8 = a2[42] - *(_QWORD *)GUID_NULL.Data4;
  if ( !v8 )
  {
    CPartnershipStateManager::LogPartnershipTelemetry((struct ClientPartnershipDescriptor *)a2, 4u);
    v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 5);
    if ( GetFileAttributesW(v9) == -1 )
    {
      v10 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 5);
      if ( !CEcsPath::CreateDirectoryRecursive(v10) )
      {
        v24 = -2134376413;
        HIWORD(v25) = 173;
        pExceptionObject = -2134376413;
        throw (long *)&pExceptionObject;
      }
      v24 = 0;
      LOWORD(v25) = 173;
    }
    pguid = 0;
    v11 = CoCreateGuid(&pguid);
    v24 = v11;
    if ( v11 < 0 )
    {
      HIWORD(v25) = 177;
      pExceptionObject = v11;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v25) = 177;
    v12 = *(_QWORD *)(a1 + 152);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 72);
    v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 52);
    (*(void (__fastcall **)(__int64, __int64, GUID *, __int64, const wchar_t *, __int64, _QWORD *, __int64))(*(_QWORD *)v12 + 16LL))(
      v12,
      v13,
      &pguid,
      v14,
      L"\\\\desktop.ini$|\\\\thumbs.db$|\\\\ehthumbs.db$|\\\\~\\$[^\\\\]*$|\\.laccdb$|\\.tmp$|\\\\635D02A9D91C401B97884B82"
       "B3BCDAEA\\.[^\\\\]*$",
      a3,
      a2 + 48,
      (__int64)a2 + 394);
    *(GUID *)(a2 + 41) = pguid;
    v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 52);
    (*(void (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v16 + 248LL))(v16, v15, a2 + 41);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 5);
      WPP_SF_S(*(_QWORD *)(v18 + 56), 16, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids, v17);
    }
    v19 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 5);
    CEcsClientNamespaceUtil::EnableWorkFoldersRegItem(v19);
    v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 5);
    v22 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *, __int64, __int64))(*(_QWORD *)v21 + 8LL))(
            v21,
            v20,
            a2 + 41,
            a3,
            a1 - 32);
    std::unique_ptr<ISyncAsClientRunner>::reset(a1 + 144, v22);
  }
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v24);
}

```

## disassembly

```asm
0x180033520  mov     [rsp-8+arg_18], rbx
0x180033525  push    rbp
0x180033526  push    rsi
0x180033527  push    rdi
0x180033528  push    r12
0x18003352a  push    r13
0x18003352c  push    r14
0x18003352e  push    r15
0x180033530  lea     rbp, [rsp-27h]
0x180033535  sub     rsp, 90h
0x18003353c  mov     rax, cs:__security_cookie
0x180033543  xor     rax, rsp
0x180033546  mov     [rbp+57h+var_38], rax
0x18003354a  mov     r12, r8
0x18003354d  mov     r14, rdx
0x180033550  mov     r13, rcx
0x180033553  lea     rcx, WPP_GLOBAL_Control
0x18003355a  mov     rax, cs:WPP_GLOBAL_Control
0x180033561  cmp     rax, rcx
0x180033564  jz      short loc_18003358E
0x180033566  test    byte ptr [rax+44h], 8
0x18003356a  jz      short loc_18003358E
0x18003356c  cmp     byte ptr [rax+41h], 6
0x180033570  jb      short loc_18003358E
0x180033572  mov     edx, 0Fh
0x180033577  lea     r8, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids
0x18003357e  mov     rcx, [rax+38h]
0x180033582  call    WPP_SF_
0x180033587  mov     rax, cs:WPP_GLOBAL_Control
0x18003358e  xor     ebx, ebx
0x180033590  test    byte ptr [rax+44h], 8
0x180033594  jz      short loc_18003359E
0x180033596  cmp     byte ptr [rax+41h], 6
0x18003359a  mov     cl, 1
0x18003359c  jnb     short loc_1800335A0
0x18003359e  mov     cl, bl
0x1800335a0  mov     [rbp+57h+var_68], ebx
0x1800335a3  mov     [rbp+57h+var_64], 92h
0x1800335aa  mov     [rbp+57h+var_60], cl
0x1800335ad  lea     rax, aCpartnershipst_7; "CPartnershipStateManager::EnsureChangeT"...
0x1800335b4  mov     [rbp+57h+var_58], rax
0x1800335b8  mov     [rbp+57h+var_50], rbx
0x1800335bc  lea     r15, [r14+148h]
0x1800335c3  mov     rax, [r15]
0x1800335c6  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800335cd  jnz     short loc_1800335DA
0x1800335cf  mov     rax, [r15+8]
0x1800335d3  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800335da  test    rax, rax
0x1800335dd  jnz     loc_1800337B5
0x1800335e3  lea     edx, [rax+4]; unsigned int
0x1800335e6  mov     rcx, r14; struct ClientPartnershipDescriptor *
0x1800335e9  call    ?LogPartnershipTelemetry@CPartnershipStateManager@@CAXAEAVClientPartnershipDescriptor@@K@Z; CPartnershipStateManager::LogPartnershipTelemetry(ClientPartnershipDescriptor &,ulong)
0x1800335ee  lea     rsi, [r14+28h]
0x1800335f2  mov     rcx, rsi
0x1800335f5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800335fa  mov     rcx, rax; lpFileName
0x1800335fd  call    cs:__imp_GetFileAttributesW
0x180033603  cmp     eax, 0FFFFFFFFh
0x180033606  jnz     short loc_18003364E
0x180033608  mov     eax, [rbp+57h+var_68]
0x18003360b  mov     [rbp+57h+var_68], eax
0x18003360e  mov     rcx, rsi
0x180033611  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180033616  mov     rcx, rax; Src
0x180033619  call    ?CreateDirectoryRecursive@CEcsPath@@SA_NPEBG@Z; CEcsPath::CreateDirectoryRecursive(ushort const *)
0x18003361e  test    al, al
0x180033620  mov     eax, 0ADh
0x180033625  jnz     short loc_180033647
0x180033627  mov     ecx, 80C80023h
0x18003362c  mov     [rbp+57h+var_68], ecx
0x18003362f  mov     word ptr [rbp+57h+var_64+2], ax
0x180033633  mov     [rbp+57h+pExceptionObject], ecx
0x180033636  lea     rdx, _TI1J; pThrowInfo
0x18003363d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180033641  call    _CxxThrowException_0
0x180033647  mov     [rbp+57h+var_68], ebx
0x18003364a  mov     word ptr [rbp+57h+var_64], ax
0x18003364e  xorps   xmm0, xmm0
0x180033651  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x180033655  lea     rcx, [rbp+57h+pguid]; pguid
0x180033659  call    cs:__imp_CoCreateGuid
0x18003365f  mov     [rbp+57h+var_68], eax
0x180033662  mov     [rbp+57h+var_68], eax
0x180033665  mov     ecx, 0B1h
0x18003366a  test    eax, eax
0x18003366c  jns     short loc_180033686
0x18003366e  mov     word ptr [rbp+57h+var_64+2], cx
0x180033672  mov     [rbp+57h+pExceptionObject], eax
0x180033675  lea     rdx, _TI1J; pThrowInfo
0x18003367c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180033680  call    _CxxThrowException_0
0x180033686  mov     word ptr [rbp+57h+var_64], cx
0x18003368a  mov     rbx, [r13+98h]
0x180033691  lea     rcx, [r13+48h]
0x180033695  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003369a  mov     r11, rax
0x18003369d  lea     rdi, [r14+1A0h]
0x1800336a4  mov     rcx, rdi
0x1800336a7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800336ac  mov     r10, rax
0x1800336af  mov     rdx, [rbx]
0x1800336b2  lea     r8, [r14+18Ah]
0x1800336b9  lea     r9, [r14+180h]
0x1800336c0  mov     rax, [rdx+10h]
0x1800336c4  mov     [rsp+0C0h+var_88], r8
0x1800336c9  mov     [rsp+0C0h+var_90], r9
0x1800336ce  mov     [rsp+0C0h+var_98], r12
0x1800336d3  lea     rcx, aDesktopIniThum; "\\\\desktop.ini$|\\\\thumbs.db$|\\\\eht"...
0x1800336da  mov     [rsp+0C0h+var_A0], rcx
0x1800336df  mov     r9, r11
0x1800336e2  lea     r8, [rbp+57h+pguid]
0x1800336e6  mov     rdx, r10
0x1800336e9  mov     rcx, rbx
0x1800336ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336f1  movups  xmm0, xmmword ptr [rbp+57h+pguid.Data1]
0x1800336f5  movdqu  xmmword ptr [r15], xmm0
0x1800336fa  mov     r10, [r13+8]
0x1800336fe  mov     rcx, rdi
0x180033701  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180033706  mov     rdx, [r10]
0x180033709  mov     r9, [rdx+0F8h]
0x180033710  mov     r8, r15
0x180033713  mov     rdx, rax
0x180033716  mov     rcx, r10
0x180033719  mov     rax, r9
0x18003371c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033721  mov     r10, cs:WPP_GLOBAL_Control
0x180033728  lea     rax, WPP_GLOBAL_Control
0x18003372f  cmp     r10, rax
0x180033732  jz      short loc_180033762
0x180033734  test    byte ptr [r10+44h], 8
0x180033739  jz      short loc_180033762
0x18003373b  cmp     byte ptr [r10+41h], 4
0x180033740  jb      short loc_180033762
0x180033742  mov     rcx, rsi
0x180033745  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003374a  mov     edx, 10h
0x18003374f  mov     r9, rax
0x180033752  lea     r8, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids
0x180033759  mov     rcx, [r10+38h]
0x18003375d  call    WPP_SF_S
0x180033762  mov     rcx, rsi
0x180033765  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003376a  mov     rcx, rax; unsigned __int16 *
0x18003376d  call    ?EnableWorkFoldersRegItem@CEcsClientNamespaceUtil@@SAJPEAG@Z; CEcsClientNamespaceUtil::EnableWorkFoldersRegItem(ushort *)
0x180033772  mov     r11, [r13+98h]
0x180033779  mov     rcx, rsi
0x18003377c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180033781  mov     rdx, [r11]
0x180033784  mov     r10, [rdx+8]
0x180033788  lea     rcx, [r13-20h]
0x18003378c  mov     [rsp+0C0h+var_A0], rcx
0x180033791  mov     r9, r12
0x180033794  mov     r8, r15
0x180033797  mov     rdx, rax
0x18003379a  mov     rcx, r11
0x18003379d  mov     rax, r10
0x1800337a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337a5  mov     rdx, rax
0x1800337a8  lea     rcx, [r13+90h]
0x1800337af  call    ?reset@?$unique_ptr@VISyncAsClientRunner@@U?$default_delete@VISyncAsClientRunner@@@std@@@std@@QEAAXPEAVISyncAsClientRunner@@@Z; std::unique_ptr<ISyncAsClientRunner>::reset(ISyncAsClientRunner *)
0x1800337b4  nop
0x1800337b5  lea     rcx, [rbp+57h+var_68]; this
0x1800337b9  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800337be  mov     rcx, [rbp+57h+var_38]
0x1800337c2  xor     rcx, rsp; StackCookie
0x1800337c5  call    __security_check_cookie
0x1800337ca  mov     rbx, [rsp+0C0h+arg_18]
0x1800337d2  add     rsp, 90h
0x1800337d9  pop     r15
0x1800337db  pop     r14
0x1800337dd  pop     r13
0x1800337df  pop     r12
0x1800337e1  pop     rdi
0x1800337e2  pop     rsi
0x1800337e3  pop     rbp
0x1800337e4  retn
```
