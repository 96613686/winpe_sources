# ScriptEngineBase::ChangeTypeFromVar(void *,ushort,tagVARIANT *)

- ea: `0x180171810`
- end: `0x180171922`
- name: `?ChangeTypeFromVar@ScriptEngineBase@@UEAAJPEAXGPEAUtagVARIANT@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(ScriptEngineBase *__hidden this, void *, unsigned __int16, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800250d4`
- `0x180026f4c`
- `0x180054858`
- `0x1801022e0`
- `0x180171810`
- `0x180221830`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180171881`
- `OLEAUT32!__imp_VariantInit` at `0x180171881`
- `OLEAUT32!__imp_VariantClear` at `0x180171910`
- `OLEAUT32!__imp_VariantClear` at `0x180171910`
- `OLEAUT32!__imp_VariantCopy` at `0x1801718e3`
- `OLEAUT32!__imp_VariantCopy` at `0x1801718e3`

## pseudocode

```c
__int64 __fastcall ScriptEngineBase::ChangeTypeFromVar(
        void (__fastcall ***this)(struct Js::ScriptContext *),
        void *a2,
        unsigned __int16 a3,
        struct tagVARIANT *a4)
{
  __int64 result; // rax
  struct tagVARIANT *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  unsigned __int64 v8; // r10
  int v9; // edi
  HRESULT v10; // eax
  unsigned __int64 v11; // [rsp+30h] [rbp-28h] BYREF
  VARIANTARG pvargSrc; // [rsp+38h] [rbp-20h] BYREF

  if ( !a4 )
    return 2147942487LL;
  v5 = a4;
  v6 = 24;
  do
  {
    LOBYTE(v5->vt) = 0;
    v5 = (struct tagVARIANT *)((char *)v5 + 1);
    --v6;
  }
  while ( v6 );
  v11 = 0;
  memset(&pvargSrc, 0, sizeof(pvargSrc));
  result = ScriptEngineBase::VerifyOnEntry((ScriptEngineBase *)this, 0);
  if ( (int)result >= 0 )
  {
    VariantInit(a4);
    if ( Js::DynamicObject::Is(a2) )
    {
      v9 = ScriptSite::ExternalToPrimitive(v8, v7, &v11, 0);
      if ( v9 < 0 )
        return (unsigned int)v9;
      v8 = v11;
    }
    v9 = DispatchHelper::MarshalJsVarToVariantNoThrow(v8, &pvargSrc, this[1]);
    if ( v9 >= 0 )
    {
      if ( a3 == 12 )
        v10 = VariantCopy(a4, &pvargSrc);
      else
        v10 = ScriptEngine::ChangeType((ScriptEngine *)(this + 24), a4, &pvargSrc, 1033, a3);
      v9 = v10;
      VariantClear(&pvargSrc);
    }
    return (unsigned int)v9;
  }
  return result;
}

```

## disassembly

```asm
0x180171810  mov     rax, rsp
0x180171813  mov     [rax+20h], r9
0x180171817  mov     [rax+18h], r8w
0x18017181c  mov     [rax+10h], rdx
0x180171820  mov     [rax+8], rcx
0x180171824  push    rbp
0x180171825  push    rsi
0x180171826  push    rdi
0x180171827  push    r14
0x180171829  mov     rbp, rsp
0x18017182c  sub     rsp, 58h
0x180171830  cmp     [rbp+pvarg], 0
0x180171835  jnz     short loc_180171841
0x180171837  mov     eax, 80070057h
0x18017183c  jmp     loc_180171918
0x180171841  mov     rax, [rbp+pvarg]
0x180171845  mov     ecx, 18h
0x18017184a  mov     byte ptr [rax], 0
0x18017184d  inc     rax
0x180171850  sub     rcx, 1
0x180171854  jnz     short loc_18017184A
0x180171856  mov     r14, [rbp+arg_0]
0x18017185a  xor     eax, eax
0x18017185c  xorps   xmm0, xmm0
0x18017185f  mov     qword ptr [rbp+pvargSrc+10h], rax
0x180171863  mov     rcx, r14; this
0x180171866  mov     [rbp+var_28], rax
0x18017186a  xor     edx, edx; int
0x18017186c  movups  xmmword ptr [rbp+pvargSrc], xmm0
0x180171870  call    ?VerifyOnEntry@ScriptEngineBase@@QEAAJH@Z; ScriptEngineBase::VerifyOnEntry(int)
0x180171875  test    eax, eax
0x180171877  js      loc_180171918
0x18017187d  mov     rcx, [rbp+pvarg]; pvarg
0x180171881  call    cs:__imp_VariantInit
0x180171887  movzx   esi, [rbp+arg_10]
0x18017188b  xor     edx, edx
0x18017188d  mov     r10, [rbp+arg_8]
0x180171891  cmp     si, 8
0x180171895  mov     rcx, r10; void *
0x180171898  setnz   dl
0x18017189b  inc     edx
0x18017189d  call    ?Is@DynamicObject@Js@@SA_NPEAX@Z; Js::DynamicObject::Is(void *)
0x1801718a2  test    al, al
0x1801718a4  jz      short loc_1801718BF
0x1801718a6  xor     r9d, r9d
0x1801718a9  lea     r8, [rbp+var_28]
0x1801718ad  mov     rcx, r10
0x1801718b0  call    ?ExternalToPrimitive@ScriptSite@@SAJPEAVRecyclableObject@Js@@UJavascriptHint@3@PEAPEAXPEAUIServiceProvider@@@Z; ScriptSite::ExternalToPrimitive(Js::RecyclableObject *,Js::JavascriptHint,void * *,IServiceProvider *)
0x1801718b5  mov     edi, eax
0x1801718b7  test    eax, eax
0x1801718b9  js      short loc_180171916
0x1801718bb  mov     r10, [rbp+var_28]
0x1801718bf  mov     r8, [r14+8]; struct Js::ScriptContext *
0x1801718c3  lea     rdx, [rbp+pvargSrc]; struct tagVARIANT *
0x1801718c7  mov     rcx, r10; void *
0x1801718ca  call    ?MarshalJsVarToVariantNoThrow@DispatchHelper@@SAJPEAXPEAUtagVARIANT@@PEAVScriptContext@Js@@@Z; DispatchHelper::MarshalJsVarToVariantNoThrow(void *,tagVARIANT *,Js::ScriptContext *)
0x1801718cf  mov     edi, eax
0x1801718d1  test    eax, eax
0x1801718d3  js      short loc_180171916
0x1801718d5  cmp     si, 0Ch
0x1801718d9  jnz     short loc_1801718EB
0x1801718db  mov     rcx, [rbp+pvarg]; pvargDest
0x1801718df  lea     rdx, [rbp+pvargSrc]; pvargSrc
0x1801718e3  call    cs:__imp_VariantCopy
0x1801718e9  jmp     short loc_18017190A
0x1801718eb  mov     rdx, [rbp+pvarg]; struct tagVARIANT *
0x1801718ef  lea     rcx, [r14+0C0h]; this
0x1801718f6  mov     r9d, 409h; unsigned int
0x1801718fc  mov     [rsp+58h+var_38], si; unsigned __int16
0x180171901  lea     r8, [rbp+pvargSrc]; struct tagVARIANT *
0x180171905  call    ?ChangeType@ScriptEngine@@UEAAJPEAUtagVARIANT@@0KG@Z; ScriptEngine::ChangeType(tagVARIANT *,tagVARIANT *,ulong,ushort)
0x18017190a  lea     rcx, [rbp+pvargSrc]; pvarg
0x18017190e  mov     edi, eax
0x180171910  call    cs:__imp_VariantClear
0x180171916  mov     eax, edi
0x180171918  add     rsp, 58h
0x18017191c  pop     r14
0x18017191e  pop     rdi
0x18017191f  pop     rsi
0x180171920  pop     rbp
0x180171921  retn
```
