# CIMRequestRAEvent::ProcessNotify(ushort *)

- ea: `0x140014894`
- end: `0x140014a8a`
- name: `?ProcessNotify@CIMRequestRAEvent@@QEAAJPEAG@Z`
- size: `502`
- prototype: `__int64 __fastcall(CIMRequestRAEvent *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140011fc0`

## callees

- `0x14000e664`
- `0x1400114c4`
- `0x140014894`
- `0x140015240`
- `0x1400156c8`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140014a4d`
- `KERNEL32!GetProcessHeap` at `0x140014a4d`
- `KERNEL32!HeapFree` at `0x140014a5b`
- `KERNEL32!HeapFree` at `0x140014a5b`
- `msvcrt!_wtoi` at `0x140014938`
- `msvcrt!_wtoi` at `0x140014938`
- `OLEAUT32!__imp_SysFreeString` at `0x140014a66`
- `OLEAUT32!__imp_SysFreeString` at `0x140014a6f`
- `OLEAUT32!__imp_SysFreeString` at `0x140014a66`
- `OLEAUT32!__imp_SysFreeString` at `0x140014a6f`

## string_xrefs

- `0x140014924`: `base\diagnosis\ra\dcom\src\publickeyexch.cpp`

## pseudocode

```c
__int64 __fastcall CIMRequestRAEvent::ProcessNotify(CIMRequestRAEvent *this, unsigned __int16 *a2)
{
  int PropertyValueFromBlob; // eax
  const struct _EVENT_DESCRIPTOR *v5; // rdx
  CEventLogger *v6; // rcx
  wchar_t *v7; // rsi
  __int64 v8; // rax
  unsigned int v9; // ebx
  int v10; // eax
  const struct _EVENT_DESCRIPTOR *v11; // rdx
  __int64 v12; // rcx
  signed int v13; // eax
  const struct _EVENT_DESCRIPTOR *v14; // rdx
  CEventLogger *v15; // rcx
  signed int v16; // eax
  const struct _EVENT_DESCRIPTOR *v17; // rdx
  CEventLogger *v18; // rcx
  __int64 v19; // rcx
  CIMRequestRA *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  HANDLE ProcessHeap; // rax
  wchar_t *String; // [rsp+30h] [rbp-20h] BYREF
  BSTR bstrString[3]; // [rsp+38h] [rbp-18h] BYREF
  int v28; // [rsp+80h] [rbp+30h] BYREF
  int v29; // [rsp+88h] [rbp+38h] BYREF

  bstrString[1] = 0;
  String = 0;
  v28 = 0;
  v29 = 0;
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, L"Termination");
  PropertyValueFromBlob = GetPropertyValueFromBlob(a2, (const struct _EVENT_DESCRIPTOR *)L"NOTIFY", &String);
  v7 = String;
  if ( PropertyValueFromBlob )
  {
    v8 = -1;
    do
      ++v8;
    while ( String[v8] );
    if ( v8 )
    {
      v10 = _wtoi(String);
      if ( ((v10 - 9) & 0xFFFFFFF7) == 0 || (v9 = 0, v10 == 1) )
      {
        v12 = *((_QWORD *)this + 1);
        if ( v12 )
        {
          v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 40LL))(v12, &v28);
          v9 = v13;
          if ( v13 >= 0 )
          {
            v16 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 1) + 96LL))(
                    *((_QWORD *)this + 1),
                    &v29);
            v9 = v16;
            if ( v16 >= 0 )
            {
              if ( v28 && v29 )
              {
                v19 = *((_QWORD *)this + 1);
                if ( v19 )
                  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, BSTR))(*(_QWORD *)v19 + 64LL))(v19, 0, bstrString[0]);
                v20 = (CIMRequestRA *)*((_QWORD *)this + 1);
                if ( v20 )
                  CIMRequestRA::ReleaseRendezvousSession(v20);
                v21 = *((_QWORD *)this + 1);
                if ( v21 )
                {
                  v22 = *(_QWORD *)(v21 + 16);
                  if ( v22 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
                    *(_QWORD *)(*((_QWORD *)this + 1) + 16LL) = 0;
                  }
                }
                v23 = *((_QWORD *)this + 1);
                if ( v23 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
                  *((_QWORD *)this + 1) = 0;
                }
              }
            }
            else
            {
              CEventLogger::LogError(
                v18,
                v17,
                L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
                0x48Eu,
                L"CIMRequestRAEvent::ProcessNotify",
                v16);
            }
          }
          else
          {
            CEventLogger::LogError(
              v15,
              v14,
              L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
              0x48Cu,
              L"CIMRequestRAEvent::ProcessNotify",
              v13);
          }
        }
        else
        {
          v9 = -2147467261;
          CEventLogger::LogError(
            0,
            v11,
            L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
            0x492u,
            L"CIMRequestRAEvent::ProcessNotify",
            0x80004003);
        }
      }
    }
    else
    {
      v9 = -2147024809;
      CEventLogger::LogError(
        v6,
        v5,
        L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
        0x47Bu,
        L"CIMRequestRAEvent::ProcessNotify",
        0x80070057);
    }
  }
  else
  {
    v9 = 0;
  }
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  SysFreeString(bstrString[0]);
  SysFreeString(0);
  return v9;
}

```

## disassembly

```asm
0x140014894  mov     [rsp-18h+arg_0], rbx
0x140014899  mov     [rsp-18h+arg_8], rsi
0x14001489e  push    rbp
0x14001489f  push    rdi
0x1400148a0  push    r14
0x1400148a2  mov     rbp, rsp
0x1400148a5  sub     rsp, 50h
0x1400148a9  mov     rbx, rdx
0x1400148ac  mov     rdi, rcx
0x1400148af  xor     r14d, r14d
0x1400148b2  mov     [rbp+var_10], r14
0x1400148b6  mov     [rbp+String], r14
0x1400148ba  mov     [rbp+arg_10], r14d
0x1400148be  mov     [rbp+arg_18], r14d
0x1400148c2  lea     rdx, aTermination; "Termination"
0x1400148c9  lea     rcx, [rbp+bstrString]; this
0x1400148cd  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1400148d2  nop
0x1400148d3  lea     r8, [rbp+String]; unsigned __int16 **
0x1400148d7  lea     rdx, aNotify; "NOTIFY"
0x1400148de  mov     rcx, rbx; String
0x1400148e1  call    ?GetPropertyValueFromBlob@@YAHPEAG0PEAPEAG@Z; GetPropertyValueFromBlob(ushort *,ushort *,ushort * *)
0x1400148e6  mov     rsi, [rbp+String]
0x1400148ea  test    eax, eax
0x1400148ec  jz      loc_140014A45
0x1400148f2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400148f6  inc     rax
0x1400148f9  cmp     [rsi+rax*2], r14w
0x1400148fe  jnz     short loc_1400148F6
0x140014900  test    rax, rax
0x140014903  jnz     short loc_140014935
0x140014905  mov     ebx, 80070057h
0x14001490a  mov     [rsp+50h+var_28], 80070057h; unsigned int
0x140014912  mov     r9d, 47Bh; unsigned int
0x140014918  lea     rax, aCimrequestraev; "CIMRequestRAEvent::ProcessNotify"
0x14001491f  mov     [rsp+50h+var_30], rax; unsigned __int16 *
0x140014924  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\dcom\\src\\publick"...
0x14001492b  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140014930  jmp     loc_140014A48
0x140014935  mov     rcx, rsi; String
0x140014938  call    cs:__imp__wtoi
0x14001493e  lea     ecx, [rax-9]
0x140014941  test    ecx, 0FFFFFFF7h
0x140014947  jz      short loc_140014955
0x140014949  mov     ebx, r14d
0x14001494c  cmp     eax, 1
0x14001494f  jnz     loc_140014A48
0x140014955  mov     rcx, [rdi+8]
0x140014959  test    rcx, rcx
0x14001495c  jz      loc_140014A2D
0x140014962  mov     rax, [rcx]
0x140014965  lea     rdx, [rbp+arg_10]
0x140014969  mov     rax, [rax+28h]
0x14001496d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014972  mov     ebx, eax
0x140014974  test    eax, eax
0x140014976  jns     short loc_140014984
0x140014978  mov     [rsp+50h+var_28], eax
0x14001497c  mov     r9d, 48Ch
0x140014982  jmp     short loc_140014918
0x140014984  mov     rcx, [rdi+8]
0x140014988  mov     rax, [rcx]
0x14001498b  lea     rdx, [rbp+arg_18]
0x14001498f  mov     rax, [rax+60h]
0x140014993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014998  mov     ebx, eax
0x14001499a  test    eax, eax
0x14001499c  jns     short loc_1400149AD
0x14001499e  mov     [rsp+50h+var_28], eax
0x1400149a2  mov     r9d, 48Eh
0x1400149a8  jmp     loc_140014918
0x1400149ad  cmp     [rbp+arg_10], r14d
0x1400149b1  jz      loc_140014A48
0x1400149b7  cmp     [rbp+arg_18], r14d
0x1400149bb  jz      loc_140014A48
0x1400149c1  mov     rcx, [rdi+8]
0x1400149c5  test    rcx, rcx
0x1400149c8  jz      short loc_1400149DE
0x1400149ca  mov     rax, [rcx]
0x1400149cd  mov     r8, [rbp+bstrString]
0x1400149d1  xor     edx, edx
0x1400149d3  mov     rax, [rax+40h]
0x1400149d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400149dc  mov     ebx, eax
0x1400149de  mov     rcx, [rdi+8]; this
0x1400149e2  test    rcx, rcx
0x1400149e5  jz      short loc_1400149EC
0x1400149e7  call    ?ReleaseRendezvousSession@CIMRequestRA@@QEAAJXZ; CIMRequestRA::ReleaseRendezvousSession(void)
0x1400149ec  mov     rax, [rdi+8]
0x1400149f0  test    rax, rax
0x1400149f3  jz      short loc_140014A12
0x1400149f5  mov     rcx, [rax+10h]
0x1400149f9  test    rcx, rcx
0x1400149fc  jz      short loc_140014A12
0x1400149fe  mov     rax, [rcx]
0x140014a01  mov     rax, [rax+10h]
0x140014a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014a0a  mov     rax, [rdi+8]
0x140014a0e  mov     [rax+10h], r14
0x140014a12  mov     rcx, [rdi+8]
0x140014a16  test    rcx, rcx
0x140014a19  jz      short loc_140014A48
0x140014a1b  mov     rax, [rcx]
0x140014a1e  mov     rax, [rax+10h]
0x140014a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014a27  mov     [rdi+8], r14
0x140014a2b  jmp     short loc_140014A48
0x140014a2d  mov     ebx, 80004003h
0x140014a32  mov     [rsp+50h+var_28], 80004003h
0x140014a3a  mov     r9d, 492h
0x140014a40  jmp     loc_140014918
0x140014a45  mov     ebx, r14d
0x140014a48  test    rsi, rsi
0x140014a4b  jz      short loc_140014A62
0x140014a4d  call    cs:__imp_GetProcessHeap
0x140014a53  mov     r8, rsi; lpMem
0x140014a56  xor     edx, edx; dwFlags
0x140014a58  mov     rcx, rax; hHeap
0x140014a5b  call    cs:__imp_HeapFree
0x140014a61  nop
0x140014a62  mov     rcx, [rbp+bstrString]; bstrString
0x140014a66  call    cs:__imp_SysFreeString
0x140014a6c  nop
0x140014a6d  xor     ecx, ecx; bstrString
0x140014a6f  call    cs:__imp_SysFreeString
0x140014a75  mov     eax, ebx
0x140014a77  mov     rbx, [rsp+50h+arg_0]
0x140014a7c  mov     rsi, [rsp+50h+arg_8]
0x140014a81  add     rsp, 50h
0x140014a85  pop     r14
0x140014a87  pop     rdi
0x140014a88  pop     rbp
0x140014a89  retn
```
