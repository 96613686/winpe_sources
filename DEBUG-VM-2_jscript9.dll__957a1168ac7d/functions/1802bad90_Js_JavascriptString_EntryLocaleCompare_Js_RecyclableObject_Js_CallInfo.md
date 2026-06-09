# Js::JavascriptString::EntryLocaleCompare(Js::RecyclableObject *,Js::CallInfo,...)

- ea: `0x1802bad90`
- end: `0x1802bafca`
- name: `?EntryLocaleCompare@JavascriptString@Js@@SAPEAXPEAVRecyclableObject@2@UCallInfo@2@ZZ`
- size: `570`
- prototype: `void *__high(struct Js::RecyclableObject *, struct Js::CallInfo, ...)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x18003f544`
- `0x1800429ec`
- `0x180043df0`
- `0x18005c708`
- `0x18005e9d0`
- `0x18005f188`
- `0x1800f99c0`
- `0x18010e730`
- `0x18015d94c`
- `0x1801a87d0`
- `0x1802bad90`
- `0x1802d4b14`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1802baf82`
- `KERNEL32!CompareStringW` at `0x1802baf82`
- `KERNEL32!GetUserDefaultLCID` at `0x1802baf69`
- `KERNEL32!GetUserDefaultLCID` at `0x1802baf69`

## string_xrefs

- `0x1802bae1d`: `String.prototype.localeCompare`
- `0x1802bae4c`: `String.prototype.localeCompare`

## pseudocode

```c
__int64 Js::JavascriptString::EntryLocaleCompare(__int64 a1, ...)
{
  ThreadContext **v2; // r8
  struct Js::ScriptContext *v3; // rdx
  __int64 v4; // rax
  int *v5; // rbx
  unsigned int v6; // r14d
  struct Js::JavascriptString **v7; // rsi
  struct Js::EngineInterfaceObject *IntlObject_EngineInterface; // rax
  struct Js::JavascriptString *v9; // r9
  struct Js::JavascriptString *v10; // rdi
  const WCHAR *OriginalStringReference; // r12
  int v12; // r13d
  const WCHAR *lpString2; // rbp
  struct Js::JavascriptString *v14; // rdi
  const WCHAR *v15; // rax
  int cchCount2; // ebx
  __int64 v17; // rcx
  LCID UserDefaultLCID; // eax
  int v20; // eax
  __int64 v21; // [rsp+40h] [rbp-68h]
  __int64 v22; // [rsp+50h] [rbp-58h] BYREF
  void **v23; // [rsp+58h] [rbp-50h]
  __int64 v24; // [rsp+B8h] [rbp+10h] BYREF
  va_list va; // [rsp+B8h] [rbp+10h]
  va_list va1; // [rsp+C0h] [rbp+18h] BYREF

  va_start(va1, a1);
  va_start(va, a1);
  v24 = va_arg(va1, _QWORD);
  v2 = *(ThreadContext ***)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1072LL);
  ThreadContext::ProbeStack(v2[148], 0x450u, (struct Js::ScriptContext *)v2, 0);
  v22 = 0;
  Js::ArgumentReader::ArgumentReader((Js::ArgumentReader *)&v22, (struct Js::CallInfo *)va, (void **)va1);
  v4 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL);
  v5 = *(int **)(v4 + 1072);
  v6 = v22 & 0xFFFFFF;
  if ( (v22 & 0xFFFFFF) == 0 )
    Js::JavascriptError::ThrowTypeError(
      *(struct Js::ScriptContext **)(v4 + 1072),
      -2146823231,
      L"String.prototype.localeCompare");
  v7 = (struct Js::JavascriptString **)v23;
  if ( v5[584] >= 3 && !(unsigned int)Js::JavascriptConversion::CheckObjectCoercible(*v23, v3) )
    Js::JavascriptError::ThrowTypeError((struct Js::ScriptContext *)v5, -2146823234, L"String.prototype.localeCompare");
  IntlObject_EngineInterface = Js::JavascriptLibraryBase::GetIntlObject_EngineInterface(*(Js::JavascriptLibraryBase **)v5);
  if ( IntlObject_EngineInterface )
  {
    if ( v6 == 2 )
    {
      v9 = *v7;
      v21 = *(_QWORD *)(*(_QWORD *)v5 + 1056LL);
      v22 = (unsigned int)v24 & 0xFF000000 | 7LL;
      Js::EngineInterfaceObject::EntryIntl_CompareString(a1, v22, v21, v9, v7[1], v21, v21, v21, v21);
    }
    else
    {
      v17 = *((_QWORD *)IntlObject_EngineInterface + 9);
      if ( v17 )
        return Js::JavascriptFunction::CallFunction(v17, &v22);
    }
  }
  v10 = *v7;
  if ( !Js::JavascriptString::Is(*v7) )
    v10 = Js::JavascriptConversion::ToString(v10, (struct Js::ScriptContext *)v5);
  OriginalStringReference = (const WCHAR *)Js::JavascriptString::GetOriginalStringReference(v10);
  v12 = *((_DWORD *)v10 + 4);
  lpString2 = (const WCHAR *)Js::JavascriptString::GetOriginalStringReference(*(Js::JavascriptString **)(*(_QWORD *)v5 + 3296LL));
  if ( v6 <= 1 )
  {
    cchCount2 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v5 + 3296LL) + 16LL);
  }
  else
  {
    v14 = v7[1];
    if ( !Js::JavascriptString::Is(v14) )
      v14 = Js::JavascriptConversion::ToString(v14, (struct Js::ScriptContext *)v5);
    v15 = (const WCHAR *)Js::JavascriptString::GetOriginalStringReference(v14);
    cchCount2 = *((_DWORD *)v14 + 4);
    lpString2 = v15;
  }
  UserDefaultLCID = GetUserDefaultLCID();
  v20 = CompareStringW(UserDefaultLCID, 0, OriginalStringReference, v12, lpString2, cchCount2);
  if ( !v20 )
    Js::JavascriptError::ThrowRangeError(
      *(struct Js::ScriptContext **)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1072LL),
      -2146828237,
      0);
  return (unsigned int)(v20 - 2) | 0x1000000000000LL;
}

```

## disassembly

```asm
0x1802bad90  mov     rax, rsp
0x1802bad93  mov     [rax+10h], rdx
0x1802bad97  mov     [rax+8], rcx
0x1802bad9b  mov     [rax+18h], r8
0x1802bad9f  mov     [rax+20h], r9
0x1802bada3  push    rbx
0x1802bada4  push    rbp
0x1802bada5  push    rsi
0x1802bada6  push    rdi
0x1802bada7  push    r12
0x1802bada9  push    r13
0x1802badab  push    r14
0x1802badad  push    r15
0x1802badaf  sub     rsp, 68h
0x1802badb3  mov     r15, [rax+8]
0x1802badb7  xor     r9d, r9d; void *
0x1802badba  mov     edx, 450h; unsigned __int64
0x1802badbf  mov     rax, [r15+8]
0x1802badc3  mov     rcx, [rax+8]
0x1802badc7  mov     rcx, [rcx+430h]
0x1802badce  mov     r8, rcx; struct Js::ScriptContext *
0x1802badd1  mov     rcx, [rcx+4A0h]; this
0x1802badd8  call    ?ProbeStack@ThreadContext@@QEAAX_KPEAVScriptContext@Js@@PEAX@Z; ThreadContext::ProbeStack(unsigned __int64,Js::ScriptContext *,void *)
0x1802baddd  lea     r8, [rsp+0A8h+arg_10]; void **
0x1802bade5  mov     qword ptr [rsp+0A8h+var_58], 0
0x1802badee  lea     rdx, [rsp+0A8h+arg_8]; struct Js::CallInfo *
0x1802badf6  lea     rcx, [rsp+0A8h+var_58]; this
0x1802badfb  call    ??0ArgumentReader@Js@@QEAA@PEAUCallInfo@1@PEAPEAX@Z; Js::ArgumentReader::ArgumentReader(Js::CallInfo *,void * *)
0x1802bae00  mov     r10, [r15+8]
0x1802bae04  mov     r14d, dword ptr [rsp+0A8h+var_58]
0x1802bae09  mov     rax, [r10+8]
0x1802bae0d  mov     rbx, [rax+430h]
0x1802bae14  and     r14d, 0FFFFFFh
0x1802bae1b  jnz     short loc_1802BAE32
0x1802bae1d  lea     r8, aStringPrototyp_10; "String.prototype.localeCompare"
0x1802bae24  mov     edx, 800A13C1h; int
0x1802bae29  mov     rcx, rbx; struct Js::ScriptContext *
0x1802bae2c  call    ?ThrowTypeError@JavascriptError@Js@@SAXPEAVScriptContext@2@JPEBG@Z; Js::JavascriptError::ThrowTypeError(Js::ScriptContext *,long,ushort const *)
0x1802bae32  cmp     dword ptr [rbx+920h], 3
0x1802bae39  mov     rsi, qword ptr [rsp+0A8h+var_58+8]
0x1802bae3e  jl      short loc_1802BAE61
0x1802bae40  mov     rcx, [rsi]; void *
0x1802bae43  call    ?CheckObjectCoercible@JavascriptConversion@Js@@SAHPEAXPEAVScriptContext@2@@Z; Js::JavascriptConversion::CheckObjectCoercible(void *,Js::ScriptContext *)
0x1802bae48  test    eax, eax
0x1802bae4a  jnz     short loc_1802BAE61
0x1802bae4c  lea     r8, aStringPrototyp_10; "String.prototype.localeCompare"
0x1802bae53  mov     edx, 800A13BEh; int
0x1802bae58  mov     rcx, rbx; struct Js::ScriptContext *
0x1802bae5b  call    ?ThrowTypeError@JavascriptError@Js@@SAXPEAVScriptContext@2@JPEBG@Z; Js::JavascriptError::ThrowTypeError(Js::ScriptContext *,long,ushort const *)
0x1802bae61  mov     rcx, [rbx]; this
0x1802bae64  call    ?GetIntlObject_EngineInterface@JavascriptLibraryBase@Js@@QEAAPEAVEngineInterfaceObject@2@XZ; Js::JavascriptLibraryBase::GetIntlObject_EngineInterface(void)
0x1802bae69  test    rax, rax
0x1802bae6c  jz      short loc_1802BAECA
0x1802bae6e  cmp     r14d, 2
0x1802bae72  jnz     loc_1802BAF3C
0x1802bae78  mov     rax, [rbx]
0x1802bae7b  mov     rcx, r15
0x1802bae7e  mov     r9, [rsi]
0x1802bae81  mov     dword ptr [rsp+0A8h+var_58+4], 0
0x1802bae89  mov     r8, [rax+420h]
0x1802bae90  mov     eax, dword ptr [rsp+0A8h+arg_8]
0x1802bae97  mov     [rsp+0A8h+var_68], r8
0x1802bae9c  and     eax, 0FF000007h
0x1802baea1  mov     [rsp+0A8h+var_70], r8
0x1802baea6  or      eax, 7
0x1802baea9  mov     dword ptr [rsp+0A8h+var_58], eax
0x1802baead  mov     rax, [rsi+8]
0x1802baeb1  mov     rdx, qword ptr [rsp+0A8h+var_58]
0x1802baeb6  mov     [rsp+0A8h+var_78], r8
0x1802baebb  mov     qword ptr [rsp+0A8h+cchCount2], r8
0x1802baec0  mov     [rsp+0A8h+lpString2], rax
0x1802baec5  call    ?EntryIntl_CompareString@EngineInterfaceObject@Js@@SAPEAXPEAVRecyclableObject@2@UCallInfo@2@ZZ; Js::EngineInterfaceObject::EntryIntl_CompareString(Js::RecyclableObject *,Js::CallInfo,...)
0x1802baeca  mov     rdi, [rsi]
0x1802baecd  mov     rcx, rdi; void *
0x1802baed0  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x1802baed5  test    al, al
0x1802baed7  jnz     short loc_1802BAEE7
0x1802baed9  mov     rdx, rbx; this
0x1802baedc  mov     rcx, rdi; void *
0x1802baedf  call    ?ToString@JavascriptConversion@Js@@SAPEAVJavascriptString@2@PEAXPEAVScriptContext@2@@Z; Js::JavascriptConversion::ToString(void *,Js::ScriptContext *)
0x1802baee4  mov     rdi, rax
0x1802baee7  mov     rcx, rdi; this
0x1802baeea  call    ?GetOriginalStringReference@JavascriptString@Js@@UEAAPEBXXZ; Js::JavascriptString::GetOriginalStringReference(void)
0x1802baeef  mov     rcx, [rbx]
0x1802baef2  mov     r12, rax
0x1802baef5  mov     r13d, [rdi+10h]
0x1802baef9  mov     rcx, [rcx+0CE0h]; this
0x1802baf00  call    ?GetOriginalStringReference@JavascriptString@Js@@UEAAPEBXXZ; Js::JavascriptString::GetOriginalStringReference(void)
0x1802baf05  mov     rbp, rax
0x1802baf08  cmp     r14d, 1
0x1802baf0c  jbe     short loc_1802BAF5C
0x1802baf0e  mov     rdi, [rsi+8]
0x1802baf12  mov     rcx, rdi; void *
0x1802baf15  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x1802baf1a  test    al, al
0x1802baf1c  jnz     short loc_1802BAF2C
0x1802baf1e  mov     rdx, rbx; this
0x1802baf21  mov     rcx, rdi; void *
0x1802baf24  call    ?ToString@JavascriptConversion@Js@@SAPEAVJavascriptString@2@PEAXPEAVScriptContext@2@@Z; Js::JavascriptConversion::ToString(void *,Js::ScriptContext *)
0x1802baf29  mov     rdi, rax
0x1802baf2c  mov     rcx, rdi; this
0x1802baf2f  call    ?GetOriginalStringReference@JavascriptString@Js@@UEAAPEBXXZ; Js::JavascriptString::GetOriginalStringReference(void)
0x1802baf34  mov     ebx, [rdi+10h]
0x1802baf37  mov     rbp, rax
0x1802baf3a  jmp     short loc_1802BAF69
0x1802baf3c  mov     rcx, [rax+48h]
0x1802baf40  test    rcx, rcx
0x1802baf43  jz      short loc_1802BAECA
0x1802baf45  movaps  xmm0, [rsp+0A8h+var_58]
0x1802baf4a  lea     rdx, [rsp+0A8h+var_58]
0x1802baf4f  movdqa  [rsp+0A8h+var_58], xmm0
0x1802baf55  call    ?CallFunction@JavascriptFunction@Js@@QEAAPEAXUArguments@2@@Z; Js::JavascriptFunction::CallFunction(Js::Arguments)
0x1802baf5a  jmp     short loc_1802BAFB9
0x1802baf5c  mov     rax, [rbx]
0x1802baf5f  mov     rcx, [rax+0CE0h]
0x1802baf66  mov     ebx, [rcx+10h]
0x1802baf69  call    cs:__imp_GetUserDefaultLCID
0x1802baf6f  mov     [rsp+0A8h+cchCount2], ebx; cchCount2
0x1802baf73  mov     r9d, r13d; cchCount1
0x1802baf76  mov     ecx, eax; Locale
0x1802baf78  mov     [rsp+0A8h+lpString2], rbp; lpString2
0x1802baf7d  mov     r8, r12; lpString1
0x1802baf80  xor     edx, edx; dwCmpFlags
0x1802baf82  call    cs:__imp_CompareStringW
0x1802baf88  test    eax, eax
0x1802baf8a  jnz     short loc_1802BAFA9
0x1802baf8c  mov     rax, [r15+8]
0x1802baf90  xor     r8d, r8d; unsigned __int16 *
0x1802baf93  mov     edx, 800A0033h; int
0x1802baf98  mov     rcx, [rax+8]
0x1802baf9c  mov     rcx, [rcx+430h]; struct Js::ScriptContext *
0x1802bafa3  call    ?ThrowRangeError@JavascriptError@Js@@SAXPEAVScriptContext@2@JPEBG@Z; Js::JavascriptError::ThrowRangeError(Js::ScriptContext *,long,ushort const *)
0x1802bafa9  add     eax, 0FFFFFFFEh
0x1802bafac  mov     rcx, 1000000000000h
0x1802bafb6  or      rax, rcx
0x1802bafb9  add     rsp, 68h
0x1802bafbd  pop     r15
0x1802bafbf  pop     r14
0x1802bafc1  pop     r13
0x1802bafc3  pop     r12
0x1802bafc5  pop     rdi
0x1802bafc6  pop     rsi
0x1802bafc7  pop     rbp
0x1802bafc8  pop     rbx
0x1802bafc9  retn
```
