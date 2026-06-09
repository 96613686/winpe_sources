# CInterceptor_IWbemSyncProvider::ExecQueryAsync(ushort * const,ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140028ef0`
- end: `0x140029250`
- name: `?ExecQueryAsync@CInterceptor_IWbemSyncProvider@@UEAAJQEAG0JPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `864`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *__hidden this, unsigned __int16 *const, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140006e0c`
- `0x14000d090`
- `0x14000d2c4`
- `0x14000fa00`
- `0x14000fa50`
- `0x14000fcb0`
- `0x14000fe70`
- `0x1400234b8`
- `0x140028ef0`
- `0x140029824`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140029009`
- `wbemcomn!GetMemLogObject` at `0x1400291f2`
- `wbemcomn!GetMemLogObject` at `0x140029009`
- `wbemcomn!GetMemLogObject` at `0x1400291f2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140029014`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400291fd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140029014`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400291fd`
- `OLEAUT32!__imp_SysAllocString` at `0x14002914e`
- `OLEAUT32!__imp_SysAllocString` at `0x14002914e`
- `OLEAUT32!__imp_SysFreeString` at `0x1400291a1`
- `OLEAUT32!__imp_SysFreeString` at `0x1400291a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInterceptor_IWbemSyncProvider::ExecQueryAsync(
        CInterceptor_IWbemSyncProvider *this,
        unsigned __int16 *const a2,
        unsigned __int16 *const a3,
        int a4,
        struct IWbemServices *a5,
        struct IWbemObjectSink *a6)
{
  struct IWbemObjectSink *v10; // r12
  struct IWbemContext *v11; // r14
  __int64 v12; // rax
  int Async; // ebx
  int v14; // ebx
  CMemoryLog *MemLogObject; // rax
  __int64 v16; // rdx
  unsigned __int16 *v17; // rsi
  CMemoryLog *v18; // rax
  int v20; // [rsp+20h] [rbp-59h]
  struct IWbemServices **v21; // [rsp+28h] [rbp-51h]
  int v22; // [rsp+40h] [rbp-39h] BYREF
  void *v23; // [rsp+48h] [rbp-31h] BYREF
  struct IWbemServices *v24; // [rsp+50h] [rbp-29h] BYREF
  struct IUnknown *v25; // [rsp+58h] [rbp-21h] BYREF
  struct IServerSecurity *v26; // [rsp+60h] [rbp-19h] BYREF
  struct IUnknown *v27; // [rsp+68h] [rbp-11h] BYREF
  _QWORD v28[10]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v29; // [rsp+D0h] [rbp+57h] BYREF

  v10 = a6;
  v11 = (struct IWbemContext *)a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSdqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      119,
      (unsigned int)WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (_DWORD)a2,
      (__int64)a3,
      a4,
      (char)a5,
      (char)a6);
  }
  if ( *((_QWORD *)this + 41) )
  {
    v12 = *((_QWORD *)this + 75);
    if ( (*(_BYTE *)(v12 + 2048) & 9) != 0 || (Async = -2147217372, *(_DWORD *)(v12 + 2032)) )
    {
      LODWORD(v23) = 0;
      v27 = 0;
      v26 = 0;
      LODWORD(v29) = 0;
      v24 = 0;
      v22 = 0;
      v25 = 0;
      v28[0] = 0;
      Async = CInterceptor_IWbemSyncProvider::Begin_IWbemServices(
                this,
                (int *)&v23,
                &v27,
                &v26,
                (int *)&v29,
                &v24,
                &v22,
                &v25);
      if ( Async >= 0 )
      {
        v14 = CMUIPreferredLanguages::Set((CMUIPreferredLanguages *)v28, v11);
        if ( v14 < 0 )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, v14);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              120,
              WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
              (unsigned int)v14);
          }
        }
        Async = CInterceptor_IWbemSyncProvider::Helper_ExecQueryAsync(
                  this,
                  (struct IUnknown *)(unsigned int)v29,
                  a2,
                  a3,
                  a4,
                  v11,
                  v10,
                  v24);
        CInterceptor_IWbemSyncProvider::End_IWbemServices(
          this,
          (int)v23,
          v27,
          v26,
          v20,
          (struct IWbemServices *)v21,
          v22,
          v25);
      }
      CMUIPreferredLanguages::~CMUIPreferredLanguages((CMUIPreferredLanguages *)v28);
LABEL_30:
      if ( Async >= 0 )
        goto LABEL_34;
    }
  }
  else if ( *((_QWORD *)this + 43) )
  {
    v23 = 0;
    LODWORD(v29) = 5;
    Async = ProviderSubSystem_Common_Globals::CreateInstance(
              &CLSID_WbemQuery,
              (struct IUnknown *)a2,
              (DWORD *)&v29,
              &IID_IWbemQuery,
              &v23);
    if ( Async >= 0 )
    {
      if ( (*(int (__fastcall **)(void *, unsigned __int16 *const, unsigned __int16 *const, _QWORD))(*(_QWORD *)v23 + 48LL))(
             v23,
             a2,
             a3,
             0) < 0 )
      {
        Async = -2147217396;
      }
      else
      {
        v29 = 0;
        if ( (*(int (__fastcall **)(void *, __int64, _QWORD, __int64 *))(*(_QWORD *)v23 + 56LL))(v23, 1, 0, &v29) < 0 )
        {
          Async = -2147217379;
        }
        else
        {
          v16 = v29;
          if ( *(_DWORD *)(v29 + 48) == 1 )
          {
            v17 = SysAllocString(**(const OLECHAR ***)(v29 + 72));
            if ( v17 )
            {
              ((void (__fastcall *)(struct IWbemObjectSink *, __int64, _QWORD, _QWORD, _QWORD))v10->lpVtbl->SetStatus)(
                v10,
                1,
                0,
                0,
                0);
              Async = CInterceptor_IWbemSyncProvider::Helper_QueryInstancesAsync(
                        this,
                        *((struct IWbemHiPerfProvider **)this + 43),
                        v17,
                        a4,
                        v11,
                        v10);
              SysFreeString(v17);
            }
            else
            {
              Async = -2147217402;
            }
            v16 = v29;
          }
          else
          {
            Async = -2147217396;
          }
          (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v23 + 64LL))(v23, v16);
        }
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
      goto LABEL_30;
    }
  }
  else
  {
    Async = -2147217398;
  }
  v18 = GetMemLogObject();
  CMemoryLog::Write(v18, Async);
LABEL_34:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      121,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)Async);
  }
  return (unsigned int)Async;
}

```

## disassembly

```asm
0x140028ef0  push    rbp
0x140028ef2  push    rbx
0x140028ef3  push    rsi
0x140028ef4  push    rdi
0x140028ef5  push    r12
0x140028ef7  push    r13
0x140028ef9  push    r14
0x140028efb  push    r15
0x140028efd  lea     rbp, [rsp-0Fh]
0x140028f02  sub     rsp, 88h
0x140028f09  mov     r13d, r9d
0x140028f0c  mov     rsi, r8
0x140028f0f  mov     r15, rdx
0x140028f12  mov     rdi, rcx
0x140028f15  lea     rax, WPP_GLOBAL_Control
0x140028f1c  mov     r12, [rbp+47h+arg_28]
0x140028f20  mov     r14, [rbp+47h+arg_20]
0x140028f24  mov     rcx, cs:WPP_GLOBAL_Control
0x140028f2b  cmp     rcx, rax
0x140028f2e  jz      short loc_140028F68
0x140028f30  test    byte ptr [rcx+1Ch], 4
0x140028f34  jz      short loc_140028F68
0x140028f36  cmp     byte ptr [rcx+19h], 5
0x140028f3a  jb      short loc_140028F68
0x140028f3c  mov     edx, 77h ; 'w'
0x140028f41  mov     [rsp+0C0h+var_88], r12
0x140028f46  mov     [rsp+0C0h+var_90], r14
0x140028f4b  mov     dword ptr [rsp+0C0h+var_98], r9d
0x140028f50  mov     [rsp+0C0h+var_A0], r8
0x140028f55  mov     r9, r15
0x140028f58  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140028f5f  mov     rcx, [rcx+10h]
0x140028f63  call    WPP_SF_SSdqq
0x140028f68  xor     ecx, ecx
0x140028f6a  cmp     [rdi+148h], rcx
0x140028f71  jz      loc_1400290AE
0x140028f77  mov     rax, [rdi+258h]
0x140028f7e  test    byte ptr [rax+800h], 9
0x140028f85  jnz     short loc_140028F98
0x140028f87  mov     ebx, 80041024h
0x140028f8c  cmp     [rax+7F0h], ecx
0x140028f92  jz      loc_1400291F2
0x140028f98  mov     dword ptr [rbp+47h+var_78], ecx
0x140028f9b  mov     [rbp+47h+var_58], rcx
0x140028f9f  mov     [rbp+47h+var_60], rcx
0x140028fa3  mov     dword ptr [rbp+47h+arg_0], ecx
0x140028fa6  mov     [rbp+47h+var_70], rcx
0x140028faa  mov     [rbp+47h+var_80], ecx
0x140028fad  mov     [rbp+47h+var_68], rcx
0x140028fb1  mov     [rbp+47h+var_50], rcx
0x140028fb5  lea     rax, [rbp+47h+var_68]
0x140028fb9  mov     [rsp+0C0h+var_88], rax; struct IUnknown **
0x140028fbe  lea     rax, [rbp+47h+var_80]
0x140028fc2  mov     [rsp+0C0h+var_90], rax; int *
0x140028fc7  lea     rax, [rbp+47h+var_70]
0x140028fcb  mov     [rsp+0C0h+var_98], rax; struct IWbemServices **
0x140028fd0  lea     rax, [rbp+47h+arg_0]
0x140028fd4  mov     [rsp+0C0h+var_A0], rax; int *
0x140028fd9  lea     r9, [rbp+47h+var_60]; struct IServerSecurity **
0x140028fdd  lea     r8, [rbp+47h+var_58]; struct IUnknown **
0x140028fe1  lea     rdx, [rbp+47h+var_78]; int *
0x140028fe5  mov     rcx, rdi; this
0x140028fe8  call    ?Begin_IWbemServices@CInterceptor_IWbemSyncProvider@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01@Z; CInterceptor_IWbemSyncProvider::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &)
0x140028fed  mov     ebx, eax
0x140028fef  test    eax, eax
0x140028ff1  js      loc_1400290A0
0x140028ff7  mov     rdx, r14; struct IWbemContext *
0x140028ffa  lea     rcx, [rbp+47h+var_50]; this
0x140028ffe  call    ?Set@CMUIPreferredLanguages@@QEAAJPEAUIWbemContext@@@Z; CMUIPreferredLanguages::Set(IWbemContext *)
0x140029003  mov     ebx, eax
0x140029005  test    eax, eax
0x140029007  jns     short loc_140029051
0x140029009  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14002900f  mov     edx, ebx
0x140029011  mov     rcx, rax
0x140029014  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14002901a  mov     rcx, cs:WPP_GLOBAL_Control
0x140029021  lea     rax, WPP_GLOBAL_Control
0x140029028  cmp     rcx, rax
0x14002902b  jz      short loc_140029051
0x14002902d  test    byte ptr [rcx+1Ch], 4
0x140029031  jz      short loc_140029051
0x140029033  cmp     byte ptr [rcx+19h], 2
0x140029037  jb      short loc_140029051
0x140029039  mov     edx, 78h ; 'x'
0x14002903e  mov     r9d, ebx
0x140029041  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140029048  mov     rcx, [rcx+10h]
0x14002904c  call    WPP_SF_d
0x140029051  mov     rax, [rbp+47h+var_70]
0x140029055  mov     [rsp+0C0h+var_88], rax; struct IWbemServices *
0x14002905a  mov     [rsp+0C0h+var_90], r12; struct IWbemObjectSink *
0x14002905f  mov     [rsp+0C0h+var_98], r14; struct IWbemServices *
0x140029064  mov     dword ptr [rsp+0C0h+var_A0], r13d; int
0x140029069  mov     r9, rsi; unsigned __int16 *
0x14002906c  mov     r8, r15; unsigned __int16 *
0x14002906f  mov     edx, dword ptr [rbp+47h+arg_0]; int
0x140029072  mov     rcx, rdi; this
0x140029075  call    ?Helper_ExecQueryAsync@CInterceptor_IWbemSyncProvider@@AEAAJHQEAG0JPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z; CInterceptor_IWbemSyncProvider::Helper_ExecQueryAsync(int,ushort * const,ushort * const,long,IWbemContext *,IWbemObjectSink *,IWbemServices *)
0x14002907a  mov     ebx, eax
0x14002907c  mov     rax, [rbp+47h+var_68]
0x140029080  mov     [rsp+0C0h+var_88], rax; struct IUnknown *
0x140029085  mov     eax, [rbp+47h+var_80]
0x140029088  mov     dword ptr [rsp+0C0h+var_90], eax; int
0x14002908c  mov     r9, [rbp+47h+var_60]; struct IServerSecurity *
0x140029090  mov     r8, [rbp+47h+var_58]; struct IUnknown *
0x140029094  mov     edx, dword ptr [rbp+47h+var_78]; int
0x140029097  mov     rcx, rdi; this
0x14002909a  call    ?End_IWbemServices@CInterceptor_IWbemSyncProvider@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemSyncProvider::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x14002909f  nop
0x1400290a0  lea     rcx, [rbp+47h+var_50]; this
0x1400290a4  call    ??1CMUIPreferredLanguages@@QEAA@XZ; CMUIPreferredLanguages::~CMUIPreferredLanguages(void)
0x1400290a9  jmp     loc_1400291E7
0x1400290ae  cmp     [rdi+158h], rcx
0x1400290b5  jz      loc_1400291ED
0x1400290bb  mov     [rbp+47h+var_78], rcx
0x1400290bf  mov     dword ptr [rbp+47h+arg_0], 5
0x1400290c6  lea     rax, [rbp+47h+var_78]
0x1400290ca  mov     [rsp+0C0h+var_A0], rax; void **
0x1400290cf  lea     r9, IID_IWbemQuery; struct _GUID *
0x1400290d6  lea     r8, [rbp+47h+arg_0]; unsigned int *
0x1400290da  lea     rcx, CLSID_WbemQuery; struct _GUID *
0x1400290e1  call    ?CreateInstance@ProviderSubSystem_Common_Globals@@SAJAEBU_GUID@@PEAUIUnknown@@AEBK0PEAPEAX@Z; ProviderSubSystem_Common_Globals::CreateInstance(_GUID const &,IUnknown *,ulong const &,_GUID const &,void * *)
0x1400290e6  mov     ebx, eax
0x1400290e8  test    eax, eax
0x1400290ea  js      loc_1400291F2
0x1400290f0  mov     rcx, [rbp+47h+var_78]
0x1400290f4  mov     rax, [rcx]
0x1400290f7  xor     r9d, r9d
0x1400290fa  mov     r8, rsi
0x1400290fd  mov     rdx, r15
0x140029100  mov     rax, [rax+30h]
0x140029104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029109  test    eax, eax
0x14002910b  js      loc_1400291D2
0x140029111  mov     [rbp+47h+arg_0], 0
0x140029119  mov     rcx, [rbp+47h+var_78]
0x14002911d  mov     rax, [rcx]
0x140029120  lea     r9, [rbp+47h+arg_0]
0x140029124  xor     r8d, r8d
0x140029127  lea     ebx, [r8+1]
0x14002912b  mov     edx, ebx
0x14002912d  mov     rax, [rax+38h]
0x140029131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029136  test    eax, eax
0x140029138  js      loc_1400291CB
0x14002913e  mov     rdx, [rbp+47h+arg_0]
0x140029142  cmp     [rdx+30h], ebx
0x140029145  jnz     short loc_1400291B4
0x140029147  mov     rcx, [rdx+48h]
0x14002914b  mov     rcx, [rcx]; psz
0x14002914e  call    cs:__imp_SysAllocString
0x140029154  mov     rsi, rax
0x140029157  test    rax, rax
0x14002915a  jz      short loc_1400291A9
0x14002915c  mov     rcx, [r12]
0x140029160  mov     rax, [rcx+20h]
0x140029164  mov     [rsp+0C0h+var_A0], 0
0x14002916d  xor     r9d, r9d
0x140029170  xor     r8d, r8d
0x140029173  mov     edx, ebx
0x140029175  mov     rcx, r12
0x140029178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002917d  mov     [rsp+0C0h+var_98], r12; struct IWbemObjectSink *
0x140029182  mov     [rsp+0C0h+var_A0], r14; struct IWbemContext *
0x140029187  mov     r9d, r13d; int
0x14002918a  mov     r8, rsi; unsigned __int16 *
0x14002918d  mov     rdx, [rdi+158h]; struct IWbemHiPerfProvider *
0x140029194  mov     rcx, rdi; this
0x140029197  call    ?Helper_QueryInstancesAsync@CInterceptor_IWbemSyncProvider@@AEAAJPEAUIWbemHiPerfProvider@@QEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z; CInterceptor_IWbemSyncProvider::Helper_QueryInstancesAsync(IWbemHiPerfProvider *,ushort * const,long,IWbemContext *,IWbemObjectSink *)
0x14002919c  mov     ebx, eax
0x14002919e  mov     rcx, rsi; bstrString
0x1400291a1  call    cs:__imp_SysFreeString
0x1400291a7  jmp     short loc_1400291AE
0x1400291a9  mov     ebx, 80041006h
0x1400291ae  mov     rdx, [rbp+47h+arg_0]
0x1400291b2  jmp     short loc_1400291B9
0x1400291b4  mov     ebx, 8004100Ch
0x1400291b9  mov     rcx, [rbp+47h+var_78]
0x1400291bd  mov     rax, [rcx]
0x1400291c0  mov     rax, [rax+40h]
0x1400291c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400291c9  jmp     short loc_1400291D7
0x1400291cb  mov     ebx, 8004101Dh
0x1400291d0  jmp     short loc_1400291D7
0x1400291d2  mov     ebx, 8004100Ch
0x1400291d7  mov     rcx, [rbp+47h+var_78]
0x1400291db  mov     rax, [rcx]
0x1400291de  mov     rax, [rax+10h]
0x1400291e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400291e7  test    ebx, ebx
0x1400291e9  js      short loc_1400291F2
0x1400291eb  jmp     short loc_140029203
0x1400291ed  mov     ebx, 8004100Ah
0x1400291f2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400291f8  mov     edx, ebx
0x1400291fa  mov     rcx, rax
0x1400291fd  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140029203  mov     rcx, cs:WPP_GLOBAL_Control
0x14002920a  lea     rax, WPP_GLOBAL_Control
0x140029211  cmp     rcx, rax
0x140029214  jz      short loc_14002923A
0x140029216  test    byte ptr [rcx+1Ch], 4
0x14002921a  jz      short loc_14002923A
0x14002921c  cmp     byte ptr [rcx+19h], 2
0x140029220  jb      short loc_14002923A
0x140029222  mov     edx, 79h ; 'y'
0x140029227  mov     r9d, ebx
0x14002922a  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140029231  mov     rcx, [rcx+10h]
0x140029235  call    WPP_SF_d
0x14002923a  mov     eax, ebx
0x14002923c  add     rsp, 88h
0x140029243  pop     r15
0x140029245  pop     r14
0x140029247  pop     r13
0x140029249  pop     r12
0x14002924b  pop     rdi
0x14002924c  pop     rsi
0x14002924d  pop     rbx
0x14002924e  pop     rbp
0x14002924f  retn
```
