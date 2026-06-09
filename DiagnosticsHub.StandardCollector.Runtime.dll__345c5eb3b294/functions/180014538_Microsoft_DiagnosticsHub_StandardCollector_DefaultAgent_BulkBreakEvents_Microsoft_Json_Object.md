# Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::BulkBreakEvents(Microsoft::Json::Object &)

- ea: `0x180014538`
- end: `0x1800146e2`
- name: `?BulkBreakEvents@DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJAEAVObject@Json@4@@Z`
- size: `426`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent *__hidden this, struct Microsoft::Json::Object *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011b60`

## callees

- `0x180014538`
- `0x1800146e4`
- `0x180014898`
- `0x1800473dc`
- `0x180047744`
- `0x1800477f8`
- `0x18004b640`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180014622`
- `OLEAUT32!__imp_SysFreeString` at `0x1800146d6`
- `OLEAUT32!__imp_SysFreeString` at `0x180014622`
- `OLEAUT32!__imp_SysFreeString` at `0x1800146d6`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x1800145d9`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x1800145fb`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x1800145d9`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x1800145fb`

## string_xrefs

- `0x1800145b1`: `command`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::BulkBreakEvents(
        Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent *this,
        struct Microsoft::Json::Object *a2)
{
  int FieldAsArray; // edi
  unsigned int v4; // esi
  __int64 v5; // r14
  wchar_t *v6; // rbx
  int v7; // eax
  volatile signed __int32 *v8; // rbx
  volatile signed __int32 *v9; // rbx
  Microsoft::Json::Object *v11[2]; // [rsp+20h] [rbp-30h] BYREF
  wchar_t *String1; // [rsp+30h] [rbp-20h] BYREF
  __int128 v13; // [rsp+38h] [rbp-18h] BYREF

  v13 = 0;
  *(_OWORD *)v11 = 0;
  FieldAsArray = Microsoft::Json::Object::GetFieldAsArray(a2, L"events", &v13);
  if ( FieldAsArray >= 0 )
  {
    v4 = 0;
    v5 = v13;
    if ( *(_DWORD *)(*(_QWORD *)v13 + 8LL) )
    {
      while ( 1 )
      {
        FieldAsArray = Microsoft::Json::Array::GetValueAsObject(v5, v4, v11);
        if ( FieldAsArray < 0 )
          break;
        String1 = 0;
        FieldAsArray = Microsoft::Json::Object::GetFieldAsString(v11[0], L"command", &String1);
        v6 = String1;
        if ( FieldAsArray < 0 )
          goto LABEL_22;
        if ( !wcscmp(String1, L"debuggerEnterBreakState") )
        {
          v7 = Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::DebuggerEnterBreakState(this, v11[0]);
        }
        else
        {
          if ( wcscmp(v6, L"debuggerExitBreakState") )
          {
            FieldAsArray = -2147024809;
LABEL_22:
            SysFreeString(v6);
            break;
          }
          v7 = Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::DebuggerExitBreakState(this, v11[0]);
        }
        FieldAsArray = v7;
        if ( v7 < 0 )
          goto LABEL_22;
        SysFreeString(v6);
        if ( ++v4 >= *(_DWORD *)(*(_QWORD *)v5 + 8LL) )
          goto LABEL_11;
      }
    }
    else
    {
LABEL_11:
      FieldAsArray = 0;
    }
  }
  v8 = (volatile signed __int32 *)v11[1];
  if ( v11[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  v9 = (volatile signed __int32 *)*((_QWORD *)&v13 + 1);
  if ( *((_QWORD *)&v13 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v13 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  return (unsigned int)FieldAsArray;
}

```

## disassembly

```asm
0x180014538  mov     [rsp-28h+arg_10], rbx
0x18001453d  push    rbp
0x18001453e  push    rsi
0x18001453f  push    rdi
0x180014540  push    r12
0x180014542  push    r14
0x180014544  mov     rbp, rsp
0x180014547  sub     rsp, 50h
0x18001454b  mov     rax, rdx
0x18001454e  mov     r12, rcx
0x180014551  xorps   xmm1, xmm1
0x180014554  movdqu  [rbp+var_18], xmm1
0x180014559  movdqu  xmmword ptr [rbp+var_30], xmm1
0x18001455e  lea     r8, [rbp+var_18]
0x180014562  lea     rdx, aEvents; "events"
0x180014569  mov     rcx, rax
0x18001456c  call    ?GetFieldAsArray@Object@Json@Microsoft@@QEAAJPEBGAEAV?$shared_ptr@VArray@Json@Microsoft@@@std@@@Z; Microsoft::Json::Object::GetFieldAsArray(ushort const *,std::shared_ptr<Microsoft::Json::Array> &)
0x180014571  mov     edi, eax
0x180014573  test    eax, eax
0x180014575  js      loc_180014638
0x18001457b  xor     esi, esi
0x18001457d  mov     r14, qword ptr [rbp+var_18]
0x180014581  mov     rax, [r14]
0x180014584  cmp     [rax+8], esi
0x180014587  jbe     loc_180014636
0x18001458d  lea     r8, [rbp+var_30]
0x180014591  mov     edx, esi
0x180014593  mov     rcx, r14
0x180014596  call    ?GetValueAsObject@Array@Json@Microsoft@@QEAAJIAEAV?$shared_ptr@VObject@Json@Microsoft@@@std@@@Z; Microsoft::Json::Array::GetValueAsObject(uint,std::shared_ptr<Microsoft::Json::Object> &)
0x18001459b  mov     edi, eax
0x18001459d  test    eax, eax
0x18001459f  js      loc_180014638
0x1800145a5  mov     [rbp+String1], 0
0x1800145ad  lea     r8, [rbp+String1]; unsigned __int16 **
0x1800145b1  lea     rdx, aCommand; "command"
0x1800145b8  mov     rcx, [rbp+var_30]; this
0x1800145bc  call    ?GetFieldAsString@Object@Json@Microsoft@@QEAAJPEBGPEAPEAG@Z; Microsoft::Json::Object::GetFieldAsString(ushort const *,ushort * *)
0x1800145c1  mov     edi, eax
0x1800145c3  mov     rbx, [rbp+String1]
0x1800145c7  test    eax, eax
0x1800145c9  js      loc_1800146D3
0x1800145cf  lea     rdx, aDebuggerenterb; "debuggerEnterBreakState"
0x1800145d6  mov     rcx, rbx; String1
0x1800145d9  call    cs:__imp_wcscmp
0x1800145df  test    eax, eax
0x1800145e1  jnz     short loc_1800145F1
0x1800145e3  mov     rdx, [rbp+var_30]; struct Microsoft::Json::Object *
0x1800145e7  mov     rcx, r12; this
0x1800145ea  call    ?DebuggerEnterBreakState@DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJAEAVObject@Json@4@@Z; Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::DebuggerEnterBreakState(Microsoft::Json::Object &)
0x1800145ef  jmp     short loc_180014615
0x1800145f1  lea     rdx, aDebuggerexitbr; "debuggerExitBreakState"
0x1800145f8  mov     rcx, rbx; String1
0x1800145fb  call    cs:__imp_wcscmp
0x180014601  test    eax, eax
0x180014603  jnz     loc_1800146CE
0x180014609  mov     rdx, [rbp+var_30]; struct Microsoft::Json::Object *
0x18001460d  mov     rcx, r12; this
0x180014610  call    ?DebuggerExitBreakState@DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJAEAVObject@Json@4@@Z; Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::DebuggerExitBreakState(Microsoft::Json::Object &)
0x180014615  test    eax, eax
0x180014617  mov     edi, eax
0x180014619  js      loc_1800146D3
0x18001461f  mov     rcx, rbx; bstrString
0x180014622  call    cs:__imp_SysFreeString
0x180014628  inc     esi
0x18001462a  mov     rax, [r14]
0x18001462d  cmp     esi, [rax+8]
0x180014630  jb      loc_18001458D
0x180014636  xor     edi, edi
0x180014638  or      esi, 0FFFFFFFFh
0x18001463b  mov     rbx, [rbp+var_30+8]
0x18001463f  test    rbx, rbx
0x180014642  jz      short loc_18001467A
0x180014644  mov     eax, esi
0x180014646  lock xadd [rbx+8], eax
0x18001464b  add     eax, esi
0x18001464d  jnz     short loc_18001467A
0x18001464f  mov     rax, [rbx]
0x180014652  mov     rcx, rbx
0x180014655  mov     rax, [rax]
0x180014658  call    cs:__guard_dispatch_icall_fptr
0x18001465e  mov     eax, esi
0x180014660  lock xadd [rbx+0Ch], eax
0x180014665  add     eax, esi
0x180014667  jnz     short loc_18001467A
0x180014669  mov     rax, [rbx]
0x18001466c  mov     rcx, rbx
0x18001466f  mov     rax, [rax+8]
0x180014673  call    cs:__guard_dispatch_icall_fptr
0x180014679  nop
0x18001467a  mov     rbx, qword ptr [rbp+var_18+8]
0x18001467e  test    rbx, rbx
0x180014681  jz      short loc_1800146B8
0x180014683  mov     eax, esi
0x180014685  lock xadd [rbx+8], eax
0x18001468a  add     eax, esi
0x18001468c  jnz     short loc_1800146B8
0x18001468e  mov     rax, [rbx]
0x180014691  mov     rcx, rbx
0x180014694  mov     rax, [rax]
0x180014697  call    cs:__guard_dispatch_icall_fptr
0x18001469d  mov     edx, esi
0x18001469f  lock xadd [rbx+0Ch], edx
0x1800146a4  add     edx, esi
0x1800146a6  jnz     short loc_1800146B8
0x1800146a8  mov     rdx, [rbx]
0x1800146ab  mov     rcx, rbx
0x1800146ae  mov     rax, [rdx+8]
0x1800146b2  call    cs:__guard_dispatch_icall_fptr
0x1800146b8  mov     eax, edi
0x1800146ba  mov     rbx, [rsp+50h+arg_10]
0x1800146c2  add     rsp, 50h
0x1800146c6  pop     r14
0x1800146c8  pop     r12
0x1800146ca  pop     rdi
0x1800146cb  pop     rsi
0x1800146cc  pop     rbp
0x1800146cd  retn
0x1800146ce  mov     edi, 80070057h
0x1800146d3  mov     rcx, rbx; bstrString
0x1800146d6  call    cs:__imp_SysFreeString
0x1800146dc  jmp     loc_180014638
```
