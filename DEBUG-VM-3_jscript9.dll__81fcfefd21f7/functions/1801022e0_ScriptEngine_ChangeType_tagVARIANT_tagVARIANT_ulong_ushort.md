# ScriptEngine::ChangeType(tagVARIANT *,tagVARIANT *,ulong,ushort)

- ea: `0x1801022e0`
- end: `0x1801024fd`
- name: `?ChangeType@ScriptEngine@@UEAAJPEAUtagVARIANT@@0KG@Z`
- size: `541`
- prototype: `__int64 __fastcall(ScriptEngine *__hidden this, struct tagVARIANT *, struct tagVARIANT *, unsigned int, unsigned __int16)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180171810`

## callees

- `0x180026f4c`
- `0x18002836c`
- `0x1801022e0`
- `0x180102504`
- `0x1801e87dc`
- `0x180221830`
- `0x18035e010`

## import_xrefs

- `msvcrt!_controlfp_s` at `0x180102366`
- `msvcrt!_controlfp_s` at `0x18010237b`
- `msvcrt!_controlfp_s` at `0x1801023c0`
- `msvcrt!_controlfp_s` at `0x180102366`
- `msvcrt!_controlfp_s` at `0x18010237b`
- `msvcrt!_controlfp_s` at `0x1801023c0`
- `OLEAUT32!__imp_VariantInit` at `0x180102314`
- `OLEAUT32!__imp_VariantInit` at `0x180102314`
- `OLEAUT32!__imp_VariantClear` at `0x1801023b1`
- `OLEAUT32!__imp_VariantClear` at `0x180102407`
- `OLEAUT32!__imp_VariantClear` at `0x1801023b1`
- `OLEAUT32!__imp_VariantClear` at `0x180102407`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1801023a5`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1801023a5`

## pseudocode

```c
errno_t __fastcall ScriptEngine::ChangeType(
        ScriptEngine *this,
        struct tagVARIANT *a2,
        struct tagVARIANT *a3,
        __int64 a4,
        unsigned __int16 a5)
{
  errno_t result; // eax
  HRESULT DispatchValue; // ebx
  VARIANTARG *p_pvarg; // rdi
  bool v8; // cc
  int v9; // edi
  int (__fastcall ***llVal)(_QWORD, GUID *, __int64 *); // rcx
  int v11; // r8d
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // r12d
  HRESULT v15; // eax
  unsigned int CurrentState; // [rsp+20h] [rbp-38h] BYREF
  __int64 v17; // [rsp+28h] [rbp-30h] BYREF
  void *v18; // [rsp+30h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-20h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  result = ScriptEngineBase::ValidateBaseThread((ScriptEngine *)((char *)this - 192));
  DispatchValue = result;
  if ( result < 0 )
    return result;
  if ( !a2 )
    return -2147467261;
  p_pvarg = a3;
  if ( !a3 )
    return -2147467261;
  CurrentState = 0;
  result = _controlfp_s(&CurrentState, 0, 0);
  v8 = result <= 0;
  if ( !result )
  {
    result = _controlfp_s(0, 0x1Fu, 0x30F031Fu);
    v8 = result <= 0;
    if ( !result )
    {
      if ( !*((_QWORD *)this - 20) )
      {
        DispatchValue = -2147418113;
        goto LABEL_10;
      }
      if ( a3->vt == a5 )
      {
LABEL_9:
        DispatchValue = VariantCopyInd(a2, p_pvarg);
LABEL_10:
        VariantClear(&pvarg);
        _controlfp_s(0, CurrentState, 0xFFFFFFFF);
        return DispatchValue;
      }
      if ( a3->vt == 9 )
      {
        llVal = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))a3->llVal;
        v17 = 0;
        if ( (**llVal)(llVal, &GUID_ebade2e2_a8cc_4797_a430_2e863867efd0, &v17) < 0 )
        {
          DispatchValue = DispatchHelper::GetDispatchValue(
                            *((struct ScriptSite **)this - 20),
                            a3->pdispVal,
                            v11,
                            &pvarg);
          p_pvarg = &pvarg;
        }
        else
        {
          v12 = v17;
          if ( v17 )
            v13 = v17 - 24;
          else
            v13 = 0;
          v18 = 0;
          if ( *(_QWORD *)(v13 + 40) )
          {
            v14 = ScriptSite::ExternalToPrimitive(*(_QWORD *)(v13 + 40), (unsigned int)(a5 != 8) + 1, &v18, 0);
            v15 = DispatchHelper::MarshalJsVarToVariantNoThrow(
                    (unsigned __int64)v18,
                    &pvarg,
                    *(void (__fastcall ***)(struct Js::ScriptContext *))(*((_QWORD *)this - 20) + 160LL));
            v12 = v17;
            p_pvarg = &pvarg;
            DispatchValue = v15;
          }
          else
          {
            DispatchValue = 0;
            v14 = -2147024891;
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          if ( DispatchValue >= 0 )
            DispatchValue = v14;
        }
        if ( p_pvarg->vt == a5 )
          goto LABEL_9;
        if ( DispatchValue < 0 )
          goto LABEL_10;
      }
      v9 = DispatchHelper::JscriptChangeType(p_pvarg, a2, a5, *((struct Js::ScriptContext *const *)this - 23));
      if ( v9 < 0 )
      {
        VariantClear(a2);
        DispatchValue = v9;
      }
      goto LABEL_10;
    }
  }
  if ( !v8 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1801022e0  mov     rax, rsp
0x1801022e3  mov     [rax+20h], r9d
0x1801022e7  mov     [rax+18h], r8
0x1801022eb  mov     [rax+10h], rdx
0x1801022ef  mov     [rax+8], rcx
0x1801022f3  push    rbp
0x1801022f4  push    rbx
0x1801022f5  push    rdi
0x1801022f6  push    r12
0x1801022f8  push    r14
0x1801022fa  push    r15
0x1801022fc  mov     rbp, rsp
0x1801022ff  sub     rsp, 58h
0x180102303  xorps   xmm0, xmm0
0x180102306  lea     rcx, [rbp+pvarg]; pvarg
0x18010230a  xor     eax, eax
0x18010230c  movups  xmmword ptr [rbp+pvarg], xmm0
0x180102310  mov     qword ptr [rbp+pvarg+10h], rax
0x180102314  call    cs:__imp_VariantInit
0x18010231a  mov     r14, [rbp+arg_0]
0x18010231e  lea     rcx, [r14-0C0h]; this
0x180102325  call    ?ValidateBaseThread@ScriptEngineBase@@IEAAJXZ; ScriptEngineBase::ValidateBaseThread(void)
0x18010232a  mov     ebx, eax
0x18010232c  test    eax, eax
0x18010232e  jns     short loc_18010233E
0x180102330  add     rsp, 58h
0x180102334  pop     r15
0x180102336  pop     r14
0x180102338  pop     r12
0x18010233a  pop     rdi
0x18010233b  pop     rbx
0x18010233c  pop     rbp
0x18010233d  retn
0x18010233e  cmp     [rbp+pvarDest], 0
0x180102343  jz      loc_1801024F3
0x180102349  mov     rdi, [rbp+pvargSrc]
0x18010234d  test    rdi, rdi
0x180102350  jz      loc_1801024F3
0x180102356  xor     r8d, r8d; Mask
0x180102359  mov     [rbp+CurrentState], 0
0x180102360  xor     edx, edx; NewValue
0x180102362  lea     rcx, [rbp+CurrentState]; CurrentState
0x180102366  call    cs:__imp__controlfp_s
0x18010236c  test    eax, eax
0x18010236e  jnz     short loc_1801023CD
0x180102370  lea     edx, [rax+1Fh]; NewValue
0x180102373  xor     ecx, ecx; CurrentState
0x180102375  mov     r8d, 30F031Fh; Mask
0x18010237b  call    cs:__imp__controlfp_s
0x180102381  test    eax, eax
0x180102383  jnz     short loc_1801023CD
0x180102385  cmp     qword ptr [r14-0A0h], 0
0x18010238d  jz      loc_180102417
0x180102393  movzx   r15d, [rbp+arg_20]
0x180102398  cmp     [rdi], r15w
0x18010239c  jnz     short loc_1801023E0
0x18010239e  mov     rcx, [rbp+pvarDest]; pvarDest
0x1801023a2  mov     rdx, rdi; pvargSrc
0x1801023a5  call    cs:__imp_VariantCopyInd
0x1801023ab  mov     ebx, eax
0x1801023ad  lea     rcx, [rbp+pvarg]; pvarg
0x1801023b1  call    cs:__imp_VariantClear
0x1801023b7  mov     edx, [rbp+CurrentState]; NewValue
0x1801023ba  or      r8d, 0FFFFFFFFh; Mask
0x1801023be  xor     ecx, ecx; CurrentState
0x1801023c0  call    cs:__imp__controlfp_s
0x1801023c6  mov     eax, ebx
0x1801023c8  jmp     loc_180102330
0x1801023cd  jle     loc_180102330
0x1801023d3  movzx   eax, ax
0x1801023d6  or      eax, 80070000h
0x1801023db  jmp     loc_180102330
0x1801023e0  cmp     word ptr [rdi], 9
0x1801023e4  jz      short loc_18010241E
0x1801023e6  mov     r9, [r14-0B8h]; struct Js::ScriptContext *
0x1801023ed  movzx   r8d, r15w; unsigned __int16
0x1801023f1  mov     rdx, [rbp+pvarDest]; struct tagVARIANT *
0x1801023f5  mov     rcx, rdi; struct tagVARIANT *
0x1801023f8  call    ?JscriptChangeType@DispatchHelper@@SAJPEAUtagVARIANT@@0GQEAVScriptContext@Js@@@Z; DispatchHelper::JscriptChangeType(tagVARIANT *,tagVARIANT *,ushort,Js::ScriptContext * const)
0x1801023fd  mov     edi, eax
0x1801023ff  test    eax, eax
0x180102401  jns     short loc_1801023AD
0x180102403  mov     rcx, [rbp+pvarDest]; pvarg
0x180102407  call    cs:__imp_VariantClear
0x18010240d  mov     ebx, edi
0x18010240f  jmp     short loc_1801023AD
0x180102411  test    ebx, ebx
0x180102413  jns     short loc_1801023E6
0x180102415  jmp     short loc_1801023AD
0x180102417  mov     ebx, 8000FFFFh
0x18010241c  jmp     short loc_1801023AD
0x18010241e  mov     rcx, [rdi+8]
0x180102422  lea     r8, [rbp+var_30]
0x180102426  mov     [rbp+var_30], 0
0x18010242e  lea     rdx, _GUID_ebade2e2_a8cc_4797_a430_2e863867efd0
0x180102435  mov     rax, [rcx]
0x180102438  mov     rax, [rax]
0x18010243b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102440  test    eax, eax
0x180102442  js      loc_1801024CA
0x180102448  mov     rcx, [rbp+var_30]
0x18010244c  test    rcx, rcx
0x18010244f  jz      short loc_180102457
0x180102451  lea     rax, [rcx-18h]
0x180102455  jmp     short loc_180102459
0x180102457  xor     eax, eax
0x180102459  xor     edx, edx
0x18010245b  mov     [rbp+var_28], 0
0x180102463  cmp     r15w, 8
0x180102468  setnz   dl
0x18010246b  inc     edx
0x18010246d  cmp     qword ptr [rax+28h], 0
0x180102472  jnz     short loc_18010247E
0x180102474  xor     ebx, ebx
0x180102476  mov     r12d, 80070005h
0x18010247c  jmp     short loc_1801024B6
0x18010247e  mov     rcx, [rax+28h]
0x180102482  lea     r8, [rbp+var_28]
0x180102486  xor     r9d, r9d
0x180102489  call    ?ExternalToPrimitive@ScriptSite@@SAJPEAVRecyclableObject@Js@@UJavascriptHint@3@PEAPEAXPEAUIServiceProvider@@@Z; ScriptSite::ExternalToPrimitive(Js::RecyclableObject *,Js::JavascriptHint,void * *,IServiceProvider *)
0x18010248e  mov     r8, [r14-0A0h]
0x180102495  lea     rdx, [rbp+pvarg]; struct tagVARIANT *
0x180102499  mov     rcx, [rbp+var_28]; void *
0x18010249d  mov     r12d, eax
0x1801024a0  mov     r8, [r8+0A0h]; struct Js::ScriptContext *
0x1801024a7  call    ?MarshalJsVarToVariantNoThrow@DispatchHelper@@SAJPEAXPEAUtagVARIANT@@PEAVScriptContext@Js@@@Z; DispatchHelper::MarshalJsVarToVariantNoThrow(void *,tagVARIANT *,Js::ScriptContext *)
0x1801024ac  mov     rcx, [rbp+var_30]
0x1801024b0  lea     rdi, [rbp+pvarg]
0x1801024b4  mov     ebx, eax
0x1801024b6  mov     rdx, [rcx]
0x1801024b9  mov     rax, [rdx+10h]
0x1801024bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801024c2  test    ebx, ebx
0x1801024c4  cmovns  ebx, r12d
0x1801024c8  jmp     short loc_1801024E4
0x1801024ca  mov     rdx, [rdi+8]; struct IDispatch *
0x1801024ce  lea     r9, [rbp+pvarg]; struct tagVARIANT *
0x1801024d2  mov     rcx, [r14-0A0h]; struct ScriptSite *
0x1801024d9  call    ?GetDispatchValue@DispatchHelper@@SAJPEAVScriptSite@@PEAUIDispatch@@JPEAUtagVARIANT@@@Z; DispatchHelper::GetDispatchValue(ScriptSite *,IDispatch *,long,tagVARIANT *)
0x1801024de  mov     ebx, eax
0x1801024e0  lea     rdi, [rbp+pvarg]
0x1801024e4  cmp     [rdi], r15w
0x1801024e8  jz      loc_18010239E
0x1801024ee  jmp     loc_180102411
0x1801024f3  mov     eax, 80004003h
0x1801024f8  jmp     loc_180102330
```
