# Microsoft::Windows::Autopilot::AutoPilotTasks::RunTask(Microsoft::WRL::ComPtr<IRegisteredTask> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Microsoft::Windows::Autopilot::AutoPilotTasks::BlockOnTaskCompletion const &)

- ea: `0x18001e450`
- end: `0x18001e833`
- name: `?RunTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEAV?$ComPtr@UIRegisteredTask@@@WRL@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUBlockOnTaskCompletion@1234@@Z`
- size: `995`
- prototype: `__int64 __fastcall(__int64 **, const OLECHAR *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016ba8`

## callees

- `0x180010764`
- `0x18001e450`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001e5a7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001e5a7`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e48e`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e48e`
- `OLEAUT32!__imp_VariantInit` at `0x18001e46d`
- `OLEAUT32!__imp_VariantInit` at `0x18001e46d`
- `OLEAUT32!__imp_VariantClear` at `0x18001e4c8`
- `OLEAUT32!__imp_VariantClear` at `0x18001e56e`
- `OLEAUT32!__imp_VariantClear` at `0x18001e620`
- `OLEAUT32!__imp_VariantClear` at `0x18001e6a2`
- `OLEAUT32!__imp_VariantClear` at `0x18001e70c`
- `OLEAUT32!__imp_VariantClear` at `0x18001e76c`
- `OLEAUT32!__imp_VariantClear` at `0x18001e7d1`
- `OLEAUT32!__imp_VariantClear` at `0x18001e80c`
- `OLEAUT32!__imp_VariantClear` at `0x18001e4c8`
- `OLEAUT32!__imp_VariantClear` at `0x18001e56e`
- `OLEAUT32!__imp_VariantClear` at `0x18001e620`
- `OLEAUT32!__imp_VariantClear` at `0x18001e6a2`
- `OLEAUT32!__imp_VariantClear` at `0x18001e70c`
- `OLEAUT32!__imp_VariantClear` at `0x18001e76c`
- `OLEAUT32!__imp_VariantClear` at `0x18001e7d1`
- `OLEAUT32!__imp_VariantClear` at `0x18001e80c`

## string_xrefs

- `0x18001e4b1`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18001e531`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18001e5e3`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18001e665`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18001e72f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18001e794`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotTasks::RunTask(__int64 **a1, const OLECHAR *a2, __int64 a3)
{
  __int64 result; // rax
  __int64 v7; // rax
  __int64 (*v8)(void); // rax
  int v9; // eax
  unsigned int v10; // ebx
  _QWORD *v11; // rcx
  int v12; // edi
  int v13; // edx
  int v14; // eax
  int v15; // eax
  const char *v16; // r9
  _QWORD *v17; // rcx
  _QWORD *v18; // rcx
  _QWORD *v19; // rcx
  _QWORD *v20; // rcx
  VARIANTARG pvarg; // [rsp+20h] [rbp-48h] BYREF
  VARIANTARG v22; // [rsp+40h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int v24; // [rsp+78h] [rbp+10h] BYREF
  _QWORD *v25; // [rsp+88h] [rbp+20h]

  VariantInit(&pvarg);
  if ( *((_QWORD *)a2 + 2) )
  {
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(const OLECHAR **)a2;
    pvarg.llVal = (LONGLONG)SysAllocString(a2);
    if ( !pvarg.llVal )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
        (const char *)0x8007000ELL,
        *(int *)&pvarg.vt);
      VariantClear(&pvarg);
      return 2147942414LL;
    }
    pvarg.vt = 8;
  }
  v25 = 0;
  v7 = **a1;
  v22 = pvarg;
  v8 = *(__int64 (**)(void))(v7 + 96);
  try
  {
    v9 = v8();
    v10 = v9;
    if ( v9 >= 0 )
    {
      if ( *(_BYTE *)a3 )
      {
        v12 = 0;
        v13 = 0;
        v24 = 0;
        while ( v13 != 3 )
        {
          if ( v12 >= *(_DWORD *)(a3 + 4) )
            break;
          Sleep(*(_DWORD *)(a3 + 8));
          v12 += *(_DWORD *)(a3 + 8);
          v14 = (*(__int64 (__fastcall **)(_QWORD *))(*v25 + 104LL))(v25);
          v10 = v14;
          if ( v14 == -2147216629 )
            break;
          if ( v14 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA5,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
              (const char *)(unsigned int)v14,
              *(int *)&pvarg.vt);
            v11 = v25;
            if ( !v25 )
              goto LABEL_23;
            goto LABEL_22;
          }
          v15 = (*(__int64 (__fastcall **)(_QWORD *, int *))(*v25 + 80LL))(v25, &v24);
          v10 = v15;
          if ( v15 == -2147216629 )
            break;
          if ( v15 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xAC,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
              (const char *)(unsigned int)v15,
              *(int *)&pvarg.vt);
            v11 = v25;
            if ( !v25 )
              goto LABEL_23;
            goto LABEL_22;
          }
          v13 = v24;
          if ( !v24 )
            goto LABEL_32;
          if ( v24 == 1 )
          {
            v17 = v25;
            if ( v25 )
            {
              v25 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v17 + 16LL))(v17);
            }
            VariantClear(&pvarg);
            return 267010;
          }
          if ( v24 != 2 && (unsigned int)(v24 - 3) >= 2 )
          {
LABEL_32:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xBC,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
              (const char *)0x8000FFFFLL,
              *(int *)&pvarg.vt);
            v18 = v25;
            if ( v25 )
            {
              v25 = 0;
              (*(void (__fastcall **)(_QWORD *, _QWORD))(*v18 + 16LL))(v18, *v18);
            }
            VariantClear(&pvarg);
            return 2147549183LL;
          }
        }
        if ( v12 <= 60000 )
          goto LABEL_39;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC1,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
          (const char *)0x800705B4LL,
          *(int *)&pvarg.vt);
        v19 = v25;
        if ( v25 )
        {
          v25 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
        }
        VariantClear(&pvarg);
        result = 2147943860LL;
      }
      else
      {
LABEL_39:
        v20 = v25;
        if ( v25 )
        {
          v25 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v20 + 16LL))(v20);
        }
        VariantClear(&pvarg);
        result = 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x95,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
        (const char *)(unsigned int)v9,
        *(int *)&pvarg.vt);
      v11 = v25;
      if ( v25 )
      {
LABEL_22:
        v25 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v11 + 16LL))(v11);
      }
LABEL_23:
      VariantClear(&pvarg);
      result = v10;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xC6,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x18001e450  mov     [rsp+arg_0], rbx
0x18001e455  mov     [rsp+arg_10], rsi
0x18001e45a  push    rdi
0x18001e45b  sub     rsp, 60h
0x18001e45f  mov     rsi, r8
0x18001e462  mov     rbx, rdx
0x18001e465  mov     rdi, rcx
0x18001e468  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001e46d  call    cs:__imp_VariantInit
0x18001e474  nop     dword ptr [rax+rax+00h]
0x18001e479  nop
0x18001e47a  cmp     qword ptr [rbx+10h], 0
0x18001e47f  jz      short loc_18001E4E5
0x18001e481  cmp     qword ptr [rbx+18h], 7
0x18001e486  jbe     short loc_18001E48B
0x18001e488  mov     rbx, [rbx]
0x18001e48b  mov     rcx, rbx; psz
0x18001e48e  call    cs:__imp_SysAllocString
0x18001e495  nop     dword ptr [rax+rax+00h]
0x18001e49a  mov     qword ptr [rsp+68h+pvarg+8], rax
0x18001e49f  test    rax, rax
0x18001e4a2  jnz     short loc_18001E4DB
0x18001e4a4  mov     rcx, [rsp+68h]; this
0x18001e4a9  mov     ebx, 8007000Eh
0x18001e4ae  mov     r9d, ebx; char *
0x18001e4b1  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001e4b8  mov     edx, 90h; void *
0x18001e4bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e4c2  nop
0x18001e4c3  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001e4c8  call    cs:__imp_VariantClear
0x18001e4cf  nop     dword ptr [rax+rax+00h]
0x18001e4d4  mov     eax, ebx
0x18001e4d6  jmp     loc_18001E820
0x18001e4db  mov     eax, 8
0x18001e4e0  mov     word ptr [rsp+68h+pvarg], ax; int
0x18001e4e5  mov     [rsp+68h+arg_18], 0
0x18001e4f1  mov     rcx, [rdi]
0x18001e4f4  mov     rax, [rcx]
0x18001e4f7  movups  xmm0, xmmword ptr [rsp+68h+pvarg]
0x18001e4fc  movaps  [rsp+68h+var_28], xmm0
0x18001e501  movsd   xmm1, qword ptr [rsp+68h+pvarg+10h]
0x18001e507  movsd   [rsp+68h+var_18], xmm1
0x18001e50d  lea     r8, [rsp+68h+arg_18]
0x18001e515  lea     rdx, [rsp+68h+var_28]
0x18001e51a  mov     rax, [rax+60h]
0x18001e51e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e523  mov     ebx, eax
0x18001e525  test    eax, eax
0x18001e527  jns     short loc_18001E581
0x18001e529  mov     rcx, [rsp+68h]; this
0x18001e52e  mov     r9d, eax; char *
0x18001e531  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001e538  mov     edx, 95h; void *
0x18001e53d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e542  nop
0x18001e543  mov     rcx, [rsp+68h+arg_18]
0x18001e54b  test    rcx, rcx
0x18001e54e  jz      short loc_18001E569
0x18001e550  mov     [rsp+68h+arg_18], 0
0x18001e55c  mov     rax, [rcx]
0x18001e55f  mov     rax, [rax+10h]
0x18001e563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e568  nop
0x18001e569  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001e56e  call    cs:__imp_VariantClear
0x18001e575  nop     dword ptr [rax+rax+00h]
0x18001e57a  mov     eax, ebx
0x18001e57c  jmp     loc_18001E820
0x18001e581  cmp     byte ptr [rsi], 0
0x18001e584  jz      loc_18001E7E1
0x18001e58a  xor     edi, edi
0x18001e58c  xor     edx, edx
0x18001e58e  mov     [rsp+68h+arg_8], edx
0x18001e592  cmp     edx, 3
0x18001e595  jz      loc_18001E77F
0x18001e59b  cmp     edi, [rsi+4]
0x18001e59e  jge     loc_18001E77F
0x18001e5a4  mov     ecx, [rsi+8]; dwMilliseconds
0x18001e5a7  call    cs:__imp_Sleep
0x18001e5ae  nop     dword ptr [rax+rax+00h]
0x18001e5b3  add     edi, [rsi+8]
0x18001e5b6  mov     rcx, [rsp+68h+arg_18]
0x18001e5be  mov     rax, [rcx]
0x18001e5c1  mov     rax, [rax+68h]
0x18001e5c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5ca  mov     ebx, eax
0x18001e5cc  cmp     eax, 8004130Bh
0x18001e5d1  jz      loc_18001E77F
0x18001e5d7  test    eax, eax
0x18001e5d9  jns     short loc_18001E633
0x18001e5db  mov     rcx, [rsp+68h]; this
0x18001e5e0  mov     r9d, eax; char *
0x18001e5e3  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001e5ea  mov     edx, 0A5h; void *
0x18001e5ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e5f4  nop
0x18001e5f5  mov     rcx, [rsp+68h+arg_18]
0x18001e5fd  test    rcx, rcx
0x18001e600  jz      short loc_18001E61B
0x18001e602  mov     [rsp+68h+arg_18], 0
0x18001e60e  mov     rax, [rcx]
0x18001e611  mov     rax, [rax+10h]
0x18001e615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e61a  nop
0x18001e61b  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001e620  call    cs:__imp_VariantClear
0x18001e627  nop     dword ptr [rax+rax+00h]
0x18001e62c  mov     eax, ebx
0x18001e62e  jmp     loc_18001E820
0x18001e633  mov     rcx, [rsp+68h+arg_18]
0x18001e63b  mov     rax, [rcx]
0x18001e63e  lea     rdx, [rsp+68h+arg_8]
0x18001e643  mov     rax, [rax+50h]
0x18001e647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e64c  mov     ebx, eax
0x18001e64e  cmp     eax, 8004130Bh
0x18001e653  jz      loc_18001E77F
0x18001e659  test    eax, eax
0x18001e65b  jns     short loc_18001E6B5
0x18001e65d  mov     rcx, [rsp+68h]; this
0x18001e662  mov     r9d, eax; char *
0x18001e665  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001e66c  mov     edx, 0ACh; void *
0x18001e671  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e676  nop
0x18001e677  mov     rcx, [rsp+68h+arg_18]
0x18001e67f  test    rcx, rcx
0x18001e682  jz      short loc_18001E69D
0x18001e684  mov     [rsp+68h+arg_18], 0
0x18001e690  mov     rax, [rcx]
0x18001e693  mov     rax, [rax+10h]
0x18001e697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e69c  nop
0x18001e69d  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001e6a2  call    cs:__imp_VariantClear
0x18001e6a9  nop     dword ptr [rax+rax+00h]
0x18001e6ae  mov     eax, ebx
0x18001e6b0  jmp     loc_18001E820
0x18001e6b5  mov     edx, [rsp+68h+arg_8]
0x18001e6b9  mov     ecx, edx
0x18001e6bb  test    edx, edx
0x18001e6bd  jz      short loc_18001E722
0x18001e6bf  sub     ecx, 1
0x18001e6c2  jz      short loc_18001E6E1
0x18001e6c4  sub     ecx, 1
0x18001e6c7  jz      loc_18001E592
0x18001e6cd  sub     ecx, 1
0x18001e6d0  jz      loc_18001E592
0x18001e6d6  cmp     ecx, 1
0x18001e6d9  jz      loc_18001E592
0x18001e6df  jmp     short loc_18001E722
0x18001e6e1  mov     rcx, [rsp+68h+arg_18]
0x18001e6e9  test    rcx, rcx
0x18001e6ec  jz      short loc_18001E707
0x18001e6ee  mov     [rsp+68h+arg_18], 0
0x18001e6fa  mov     rax, [rcx]
0x18001e6fd  mov     rax, [rax+10h]
0x18001e701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e706  nop
0x18001e707  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001e70c  call    cs:__imp_VariantClear
0x18001e713  nop     dword ptr [rax+rax+00h]
0x18001e718  mov     eax, 41302h
0x18001e71d  jmp     loc_18001E820
0x18001e722  mov     rcx, [rsp+68h]; this
0x18001e727  mov     ebx, 8000FFFFh
0x18001e72c  mov     r9d, ebx; char *
0x18001e72f  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001e736  mov     edx, 0BCh; void *
0x18001e73b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e740  nop
0x18001e741  mov     rcx, [rsp+68h+arg_18]
0x18001e749  test    rcx, rcx
0x18001e74c  jz      short loc_18001E767
0x18001e74e  mov     [rsp+68h+arg_18], 0
0x18001e75a  mov     rdx, [rcx]
0x18001e75d  mov     rax, [rdx+10h]
0x18001e761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e766  nop
0x18001e767  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001e76c  call    cs:__imp_VariantClear
0x18001e773  nop     dword ptr [rax+rax+00h]
0x18001e778  mov     eax, ebx
0x18001e77a  jmp     loc_18001E820
0x18001e77f  cmp     edi, 0EA60h
0x18001e785  jle     short loc_18001E7E1
0x18001e787  mov     rcx, [rsp+68h]; this
0x18001e78c  mov     ebx, 800705B4h
0x18001e791  mov     r9d, ebx; char *
0x18001e794  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001e79b  mov     edx, 0C1h; void *
0x18001e7a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e7a5  nop
0x18001e7a6  mov     rcx, [rsp+68h+arg_18]
0x18001e7ae  test    rcx, rcx
0x18001e7b1  jz      short loc_18001E7CC
0x18001e7b3  mov     [rsp+68h+arg_18], 0
0x18001e7bf  mov     rdx, [rcx]
0x18001e7c2  mov     rax, [rdx+10h]
0x18001e7c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7cb  nop
0x18001e7cc  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001e7d1  call    cs:__imp_VariantClear
0x18001e7d8  nop     dword ptr [rax+rax+00h]
0x18001e7dd  mov     eax, ebx
0x18001e7df  jmp     short loc_18001E820
0x18001e7e1  mov     rcx, [rsp+68h+arg_18]
0x18001e7e9  test    rcx, rcx
0x18001e7ec  jz      short loc_18001E807
0x18001e7ee  mov     [rsp+68h+arg_18], 0
0x18001e7fa  mov     rax, [rcx]
0x18001e7fd  mov     rax, [rax+10h]
0x18001e801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e806  nop
0x18001e807  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001e80c  call    cs:__imp_VariantClear
0x18001e813  nop     dword ptr [rax+rax+00h]
0x18001e818  xor     eax, eax
0x18001e81a  jmp     short loc_18001E820
0x18001e81c  mov     eax, [rsp+68h+arg_8]
0x18001e820  lea     r11, [rsp+68h+var_8]
0x18001e825  mov     rbx, [r11+10h]
0x18001e829  mov     rsi, [r11+20h]
0x18001e82d  mov     rsp, r11
0x18001e830  pop     rdi
0x18001e831  retn
```
