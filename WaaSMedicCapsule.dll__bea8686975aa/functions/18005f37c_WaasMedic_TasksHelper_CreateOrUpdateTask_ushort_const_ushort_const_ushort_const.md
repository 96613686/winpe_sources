# WaasMedic::TasksHelper::CreateOrUpdateTask(ushort const *,ushort const *,ushort const *)

- ea: `0x18005f37c`
- end: `0x18005f683`
- name: `?CreateOrUpdateTask@TasksHelper@WaasMedic@@QEAAJPEBG00@Z`
- size: `775`
- prototype: `int(WaasMedic::TasksHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180055b30`
- `0x18005acb8`

## callees

- `0x180002150`
- `0x180009a54`
- `0x180016c9c`
- `0x18002543c`
- `0x18005f37c`
- `0x180064010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18005f3c5`
- `OLEAUT32!__imp_SysAllocString` at `0x18005f3e6`
- `OLEAUT32!__imp_SysAllocString` at `0x18005f3c5`
- `OLEAUT32!__imp_SysAllocString` at `0x18005f3e6`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f647`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f651`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f647`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f651`
- `OLEAUT32!__imp_VariantInit` at `0x18005f406`
- `OLEAUT32!__imp_VariantInit` at `0x18005f48f`
- `OLEAUT32!__imp_VariantInit` at `0x18005f4a3`
- `OLEAUT32!__imp_VariantInit` at `0x18005f406`
- `OLEAUT32!__imp_VariantInit` at `0x18005f48f`
- `OLEAUT32!__imp_VariantInit` at `0x18005f4a3`
- `OLEAUT32!__imp_VariantClear` at `0x18005f43a`
- `OLEAUT32!__imp_VariantClear` at `0x18005f51c`
- `OLEAUT32!__imp_VariantClear` at `0x18005f527`
- `OLEAUT32!__imp_VariantClear` at `0x18005f619`
- `OLEAUT32!__imp_VariantClear` at `0x18005f43a`
- `OLEAUT32!__imp_VariantClear` at `0x18005f51c`
- `OLEAUT32!__imp_VariantClear` at `0x18005f527`
- `OLEAUT32!__imp_VariantClear` at `0x18005f619`

## string_xrefs

- `0x18005f423`: `onecore\enduser\waasmedic\lib\util\taskshelper.cpp`
- `0x18005f602`: `taskXml: %s`
- `0x18005f53b`: `Failed to create or update task %s! hr = 0x%08x`
- `0x18005f5f0`: `TasksHelper: Error encountered when attempting to create or update %s. hr = 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WaasMedic::TasksHelper::CreateOrUpdateTask(
        WaasMedic::TasksHelper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  OLECHAR *v7; // rdi
  OLECHAR *v8; // rbx
  unsigned int v9; // esi
  __int64 v10; // rcx
  __int64 v11; // r14
  __int64 (__fastcall *v12)(__int64, OLECHAR *, OLECHAR *, __int64, VARIANTARG *, __int128 *, int, __int128 *, __int64 *); // rsi
  __int128 v13; // xmm8
  IRecordInfo *pRecInfo; // xmm9_8
  __int128 v15; // xmm6
  IRecordInfo *v16; // xmm7_8
  const struct _tlgProvider_t *v17; // rax
  int v18; // r9d
  __int64 v19; // rcx
  int v21; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v22; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *v23; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v24; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG v27; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG v28; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v29; // [rsp+C0h] [rbp-40h] BYREF
  IRecordInfo *v30; // [rsp+D0h] [rbp-30h]
  __int128 v31; // [rsp+E0h] [rbp-20h] BYREF
  IRecordInfo *v32; // [rsp+F0h] [rbp-10h]
  VARIANTARG v33; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]
  __int64 v35; // [rsp+1A0h] [rbp+A0h] BYREF
  OLECHAR *v36; // [rsp+1A8h] [rbp+A8h]
  OLECHAR *v37; // [rsp+1B0h] [rbp+B0h]
  const unsigned __int16 *v38; // [rsp+1B8h] [rbp+B8h] BYREF

  v38 = a4;
  v7 = 0;
  v36 = 0;
  if ( a2 )
  {
    v7 = SysAllocString(a2);
    v36 = v7;
  }
  v8 = 0;
  v37 = 0;
  if ( a3 )
  {
    v8 = SysAllocString(a3);
    v37 = v8;
  }
  v35 = 0;
  VariantInit(&pvarg);
  if ( *((_BYTE *)this + 17) )
  {
    pvarg.vt = 0;
    v11 = *((_QWORD *)this + 1);
    v12 = *(__int64 (__fastcall **)(__int64, OLECHAR *, OLECHAR *, __int64, VARIANTARG *, __int128 *, int, __int128 *, __int64 *))(*(_QWORD *)v11 + 128LL);
    v13 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v28);
    v15 = *(_OWORD *)&v28.vt;
    v16 = v28.pRecInfo;
    VariantInit(&v27);
    v29 = v13;
    v30 = pRecInfo;
    v31 = v15;
    v32 = v16;
    v33 = v27;
    v9 = v12(v11, v7, v8, 6, &v33, &v31, 5, &v29, &v35);
    VariantClear(&v27);
    VariantClear(&v28);
    if ( (v9 & 0x80000000) != 0 )
    {
      LogLevelW(2u, L"Failed to create or update task %s! hr = 0x%08x", a2, v9);
      v17 = WaasMedic::TelemetryProvider::Provider();
      if ( *(_DWORD *)v17 > 5u
        && (*((_QWORD *)v17 + 2) & 0x400000000000LL) != 0
        && (*((_QWORD *)v17 + 3) & 0x400000000000LL) == *((_QWORD *)v17 + 3) )
      {
        LODWORD(v38) = v9;
        v22 = a3;
        v23 = a2;
        v24 = &gc_pszVersionString;
        v25 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (_DWORD)v17,
          (unsigned int)&dword_18008A54C,
          0,
          v18,
          (__int64)&v25,
          (__int64)&v24,
          (__int64)&v23,
          (__int64)&v22,
          (__int64)&v38);
      }
      LogLevelW(2u, L"TasksHelper: Error encountered when attempting to create or update %s. hr = 0x%08X", a2, v9);
      LogLevelW(4u, L"taskXml: %s", a3);
    }
    VariantClear(&pvarg);
    v19 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
  }
  else
  {
    v9 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x165,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\taskshelper.cpp",
      (const char *)0x8007139FLL,
      v21);
    VariantClear(&pvarg);
    v10 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
  SysFreeString(v8);
  SysFreeString(v7);
  return v9;
}

```

## disassembly

```asm
0x18005f37c  mov     rax, rsp
0x18005f37f  mov     [rax+20h], r9
0x18005f383  push    rbp
0x18005f384  push    rbx
0x18005f385  push    rsi
0x18005f386  push    rdi
0x18005f387  push    r12
0x18005f389  push    r14
0x18005f38b  push    r15
0x18005f38d  lea     rbp, [rsp-60h]
0x18005f392  sub     rsp, 160h
0x18005f399  movaps  xmmword ptr [rax-48h], xmm6
0x18005f39d  movaps  xmmword ptr [rax-58h], xmm7
0x18005f3a1  movaps  xmmword ptr [rax-68h], xmm8
0x18005f3a6  movaps  xmmword ptr [rax-78h], xmm9
0x18005f3ab  mov     r12, r8
0x18005f3ae  mov     r15, rdx
0x18005f3b1  mov     r14, rcx
0x18005f3b4  xor     edi, edi
0x18005f3b6  mov     [rbp+90h+arg_8], rdi
0x18005f3bd  test    rdx, rdx
0x18005f3c0  jz      short loc_18005F3D5
0x18005f3c2  mov     rcx, rdx; psz
0x18005f3c5  call    cs:__imp_SysAllocString
0x18005f3cb  mov     rdi, rax
0x18005f3ce  mov     [rbp+90h+arg_8], rax
0x18005f3d5  xor     ebx, ebx
0x18005f3d7  mov     [rbp+90h+arg_10], rbx
0x18005f3de  test    r12, r12
0x18005f3e1  jz      short loc_18005F3F6
0x18005f3e3  mov     rcx, r12; psz
0x18005f3e6  call    cs:__imp_SysAllocString
0x18005f3ec  mov     rbx, rax
0x18005f3ef  mov     [rbp+90h+arg_10], rax
0x18005f3f6  mov     [rbp+90h+arg_0], 0
0x18005f401  lea     rcx, [rsp+190h+pvarg]; pvarg
0x18005f406  call    cs:__imp_VariantInit
0x18005f40c  nop
0x18005f40d  cmp     byte ptr [r14+11h], 0
0x18005f412  jnz     short loc_18005F46A
0x18005f414  mov     rcx, [rbp+98h]; this
0x18005f41b  mov     esi, 8007139Fh
0x18005f420  mov     r9d, esi; char *
0x18005f423  lea     r8, aOnecoreEnduser_18; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18005f42a  mov     edx, 165h; void *
0x18005f42f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f434  nop
0x18005f435  lea     rcx, [rsp+190h+pvarg]; pvarg
0x18005f43a  call    cs:__imp_VariantClear
0x18005f440  nop
0x18005f441  mov     rcx, [rbp+90h+arg_0]
0x18005f448  test    rcx, rcx
0x18005f44b  jz      short loc_18005F465
0x18005f44d  mov     [rbp+90h+arg_0], 0
0x18005f458  mov     rax, [rcx]
0x18005f45b  mov     rax, [rax+10h]
0x18005f45f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f464  nop
0x18005f465  jmp     loc_18005F644
0x18005f46a  xor     eax, eax
0x18005f46c  mov     word ptr [rsp+190h+pvarg], ax
0x18005f471  mov     r14, [r14+8]
0x18005f475  mov     rax, [r14]
0x18005f478  mov     rsi, [rax+80h]
0x18005f47f  movups  xmm8, xmmword ptr [rsp+190h+pvarg]
0x18005f485  movsd   xmm9, qword ptr [rbp+90h+pvarg+10h]
0x18005f48b  lea     rcx, [rbp+90h+var_F0]; pvarg
0x18005f48f  call    cs:__imp_VariantInit
0x18005f495  nop
0x18005f496  movups  xmm6, xmmword ptr [rbp+90h+var_F0]
0x18005f49a  movsd   xmm7, qword ptr [rbp+90h+var_F0+10h]
0x18005f49f  lea     rcx, [rbp+90h+var_108]; pvarg
0x18005f4a3  call    cs:__imp_VariantInit
0x18005f4a9  nop
0x18005f4aa  movups  xmm0, xmmword ptr [rbp+90h+var_108]
0x18005f4ae  movsd   xmm1, qword ptr [rbp+90h+var_108+10h]
0x18005f4b3  movaps  [rbp+90h+var_D0], xmm8
0x18005f4b8  movsd   [rbp+90h+var_C0], xmm9
0x18005f4be  movaps  [rbp+90h+var_B0], xmm6
0x18005f4c2  movsd   [rbp+90h+var_A0], xmm7
0x18005f4c7  movaps  [rbp+90h+var_90], xmm0
0x18005f4cb  movsd   [rbp+90h+var_80], xmm1
0x18005f4d0  lea     rax, [rbp+90h+arg_0]
0x18005f4d7  mov     [rsp+190h+var_150], rax
0x18005f4dc  lea     rax, [rbp+90h+var_D0]
0x18005f4e0  mov     [rsp+190h+var_158], rax
0x18005f4e5  mov     dword ptr [rsp+190h+var_160], 5
0x18005f4ed  lea     rax, [rbp+90h+var_B0]
0x18005f4f1  mov     [rsp+190h+var_168], rax
0x18005f4f6  lea     rax, [rbp+90h+var_90]
0x18005f4fa  mov     [rsp+190h+var_170], rax
0x18005f4ff  mov     r9d, 6
0x18005f505  mov     r8, rbx
0x18005f508  mov     rdx, rdi
0x18005f50b  mov     rcx, r14
0x18005f50e  mov     rax, rsi
0x18005f511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f516  mov     esi, eax
0x18005f518  lea     rcx, [rbp+90h+var_108]; pvarg
0x18005f51c  call    cs:__imp_VariantClear
0x18005f522  nop
0x18005f523  lea     rcx, [rbp+90h+var_F0]; pvarg
0x18005f527  call    cs:__imp_VariantClear
0x18005f52d  test    esi, esi
0x18005f52f  jns     loc_18005F614
0x18005f535  mov     r9d, esi
0x18005f538  mov     r8, r15
0x18005f53b  lea     rdx, aFailedToCreate_5; "Failed to create or update task %s! hr "...
0x18005f542  mov     r14d, 2
0x18005f548  mov     ecx, r14d; unsigned __int8
0x18005f54b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005f550  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x18005f555  mov     ecx, [rax]
0x18005f557  cmp     ecx, 5
0x18005f55a  jbe     loc_18005F5EA
0x18005f560  mov     rdx, [rax+18h]
0x18005f564  mov     rcx, [rax+10h]
0x18005f568  mov     r8, 400000000000h
0x18005f572  test    r8, rcx
0x18005f575  jz      short loc_18005F5EA
0x18005f577  mov     rcx, rdx
0x18005f57a  and     rcx, r8
0x18005f57d  cmp     rcx, rdx
0x18005f580  jnz     short loc_18005F5EA
0x18005f582  mov     dword ptr [rbp+90h+arg_18], esi
0x18005f588  mov     [rsp+190h+var_140], r12
0x18005f58d  mov     [rsp+190h+var_138], r15
0x18005f592  lea     rcx, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x18005f599  mov     [rsp+190h+var_130], rcx
0x18005f59e  mov     [rsp+190h+var_128], 1000000h
0x18005f5a7  lea     rcx, [rbp+90h+arg_18]
0x18005f5ae  mov     [rsp+190h+var_150], rcx
0x18005f5b3  lea     rcx, [rsp+190h+var_140]
0x18005f5b8  mov     [rsp+190h+var_158], rcx
0x18005f5bd  lea     rdx, [rsp+190h+var_138]
0x18005f5c2  mov     [rsp+190h+var_160], rdx
0x18005f5c7  lea     rdx, [rsp+190h+var_130]
0x18005f5cc  mov     [rsp+190h+var_168], rdx
0x18005f5d1  lea     rdx, [rsp+190h+var_128]
0x18005f5d6  mov     [rsp+190h+var_170], rdx
0x18005f5db  lea     rdx, dword_18008A54C
0x18005f5e2  mov     rcx, rax
0x18005f5e5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18005f5ea  mov     r9d, esi
0x18005f5ed  mov     r8, r15
0x18005f5f0  lea     rdx, aTaskshelperErr; "TasksHelper: Error encountered when att"...
0x18005f5f7  mov     ecx, r14d; unsigned __int8
0x18005f5fa  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005f5ff  mov     r8, r12
0x18005f602  lea     rdx, aTaskxmlS; "taskXml: %s"
0x18005f609  mov     ecx, 4; unsigned __int8
0x18005f60e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005f613  nop
0x18005f614  lea     rcx, [rsp+190h+pvarg]; pvarg
0x18005f619  call    cs:__imp_VariantClear
0x18005f61f  nop
0x18005f620  mov     rcx, [rbp+90h+arg_0]
0x18005f627  test    rcx, rcx
0x18005f62a  jz      short loc_18005F644
0x18005f62c  mov     [rbp+90h+arg_0], 0
0x18005f637  mov     rax, [rcx]
0x18005f63a  mov     rax, [rax+10h]
0x18005f63e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f643  nop
0x18005f644  mov     rcx, rbx; bstrString
0x18005f647  call    cs:__imp_SysFreeString
0x18005f64d  nop
0x18005f64e  mov     rcx, rdi; bstrString
0x18005f651  call    cs:__imp_SysFreeString
0x18005f657  mov     eax, esi
0x18005f659  lea     r11, [rsp+190h+var_30]
0x18005f661  movaps  xmm6, xmmword ptr [r11-10h]
0x18005f666  movaps  xmm7, xmmword ptr [r11-20h]
0x18005f66b  movaps  xmm8, xmmword ptr [r11-30h]
0x18005f670  movaps  xmm9, xmmword ptr [r11-40h]
0x18005f675  mov     rsp, r11
0x18005f678  pop     r15
0x18005f67a  pop     r14
0x18005f67c  pop     r12
0x18005f67e  pop     rdi
0x18005f67f  pop     rsi
0x18005f680  pop     rbx
0x18005f681  pop     rbp
0x18005f682  retn
```
