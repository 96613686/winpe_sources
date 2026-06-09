# Microsoft::Windows::Autopilot::AutoPilotTasks::RunTask(Microsoft::WRL::ComPtr<IRegisteredTask> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Microsoft::Windows::Autopilot::AutoPilotTasks::BlockOnTaskCompletion const &)

- ea: `0x18001dc64`
- end: `0x18001e005`
- name: `?RunTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEAV?$ComPtr@UIRegisteredTask@@@WRL@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUBlockOnTaskCompletion@1234@@Z`
- size: `929`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016700`

## callees

- `0x1800105f4`
- `0x18001dc64`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001dda3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001dda3`
- `OLEAUT32!__imp_SysAllocString` at `0x18001dc9c`
- `OLEAUT32!__imp_SysAllocString` at `0x18001dc9c`
- `OLEAUT32!__imp_VariantInit` at `0x18001dc81`
- `OLEAUT32!__imp_VariantInit` at `0x18001dc81`
- `OLEAUT32!__imp_VariantClear` at `0x18001dcd0`
- `OLEAUT32!__imp_VariantClear` at `0x18001dd70`
- `OLEAUT32!__imp_VariantClear` at `0x18001de16`
- `OLEAUT32!__imp_VariantClear` at `0x18001de92`
- `OLEAUT32!__imp_VariantClear` at `0x18001def6`
- `OLEAUT32!__imp_VariantClear` at `0x18001df50`
- `OLEAUT32!__imp_VariantClear` at `0x18001dfaf`
- `OLEAUT32!__imp_VariantClear` at `0x18001dfe4`
- `OLEAUT32!__imp_VariantClear` at `0x18001dcd0`
- `OLEAUT32!__imp_VariantClear` at `0x18001dd70`
- `OLEAUT32!__imp_VariantClear` at `0x18001de16`
- `OLEAUT32!__imp_VariantClear` at `0x18001de92`
- `OLEAUT32!__imp_VariantClear` at `0x18001def6`
- `OLEAUT32!__imp_VariantClear` at `0x18001df50`
- `OLEAUT32!__imp_VariantClear` at `0x18001dfaf`
- `OLEAUT32!__imp_VariantClear` at `0x18001dfe4`

## string_xrefs

- `0x18001dcb9`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18001dd33`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18001ddd9`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18001de55`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18001df13`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18001df72`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x18001dc64  mov     [rsp+arg_0], rbx
0x18001dc69  mov     [rsp+arg_10], rsi
0x18001dc6e  push    rdi
0x18001dc6f  sub     rsp, 60h
0x18001dc73  mov     rsi, r8
0x18001dc76  mov     rbx, rdx
0x18001dc79  mov     rdi, rcx
0x18001dc7c  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001dc81  call    cs:__imp_VariantInit
0x18001dc87  nop
0x18001dc88  cmp     qword ptr [rbx+10h], 0
0x18001dc8d  jz      short loc_18001DCE7
0x18001dc8f  cmp     qword ptr [rbx+18h], 7
0x18001dc94  jbe     short loc_18001DC99
0x18001dc96  mov     rbx, [rbx]
0x18001dc99  mov     rcx, rbx; psz
0x18001dc9c  call    cs:__imp_SysAllocString
0x18001dca2  mov     qword ptr [rsp+68h+pvarg+8], rax
0x18001dca7  test    rax, rax
0x18001dcaa  jnz     short loc_18001DCDD
0x18001dcac  mov     rcx, [rsp+68h]; this
0x18001dcb1  mov     ebx, 8007000Eh
0x18001dcb6  mov     r9d, ebx; char *
0x18001dcb9  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001dcc0  mov     edx, 90h; void *
0x18001dcc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dcca  nop
0x18001dccb  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001dcd0  call    cs:__imp_VariantClear
0x18001dcd6  mov     eax, ebx
0x18001dcd8  jmp     loc_18001DFF2
0x18001dcdd  mov     eax, 8
0x18001dce2  mov     word ptr [rsp+68h+pvarg], ax; int
0x18001dce7  mov     [rsp+68h+arg_18], 0
0x18001dcf3  mov     rcx, [rdi]
0x18001dcf6  mov     rax, [rcx]
0x18001dcf9  movups  xmm0, xmmword ptr [rsp+68h+pvarg]
0x18001dcfe  movaps  [rsp+68h+var_28], xmm0
0x18001dd03  movsd   xmm1, qword ptr [rsp+68h+pvarg+10h]
0x18001dd09  movsd   [rsp+68h+var_18], xmm1
0x18001dd0f  lea     r8, [rsp+68h+arg_18]
0x18001dd17  lea     rdx, [rsp+68h+var_28]
0x18001dd1c  mov     rax, [rax+60h]
0x18001dd20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd25  mov     ebx, eax
0x18001dd27  test    eax, eax
0x18001dd29  jns     short loc_18001DD7D
0x18001dd2b  mov     rcx, [rsp+68h]; this
0x18001dd30  mov     r9d, eax; char *
0x18001dd33  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001dd3a  mov     edx, 95h; void *
0x18001dd3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dd44  nop
0x18001dd45  mov     rcx, [rsp+68h+arg_18]
0x18001dd4d  test    rcx, rcx
0x18001dd50  jz      short loc_18001DD6B
0x18001dd52  mov     [rsp+68h+arg_18], 0
0x18001dd5e  mov     rax, [rcx]
0x18001dd61  mov     rax, [rax+10h]
0x18001dd65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd6a  nop
0x18001dd6b  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001dd70  call    cs:__imp_VariantClear
0x18001dd76  mov     eax, ebx
0x18001dd78  jmp     loc_18001DFF2
0x18001dd7d  cmp     byte ptr [rsi], 0
0x18001dd80  jz      loc_18001DFB9
0x18001dd86  xor     edi, edi
0x18001dd88  xor     edx, edx
0x18001dd8a  mov     [rsp+68h+arg_8], edx
0x18001dd8e  cmp     edx, 3
0x18001dd91  jz      loc_18001DF5D
0x18001dd97  cmp     edi, [rsi+4]
0x18001dd9a  jge     loc_18001DF5D
0x18001dda0  mov     ecx, [rsi+8]; dwMilliseconds
0x18001dda3  call    cs:__imp_Sleep
0x18001dda9  add     edi, [rsi+8]
0x18001ddac  mov     rcx, [rsp+68h+arg_18]
0x18001ddb4  mov     rax, [rcx]
0x18001ddb7  mov     rax, [rax+68h]
0x18001ddbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ddc0  mov     ebx, eax
0x18001ddc2  cmp     eax, 8004130Bh
0x18001ddc7  jz      loc_18001DF5D
0x18001ddcd  test    eax, eax
0x18001ddcf  jns     short loc_18001DE23
0x18001ddd1  mov     rcx, [rsp+68h]; this
0x18001ddd6  mov     r9d, eax; char *
0x18001ddd9  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001dde0  mov     edx, 0A5h; void *
0x18001dde5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ddea  nop
0x18001ddeb  mov     rcx, [rsp+68h+arg_18]
0x18001ddf3  test    rcx, rcx
0x18001ddf6  jz      short loc_18001DE11
0x18001ddf8  mov     [rsp+68h+arg_18], 0
0x18001de04  mov     rax, [rcx]
0x18001de07  mov     rax, [rax+10h]
0x18001de0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de10  nop
0x18001de11  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001de16  call    cs:__imp_VariantClear
0x18001de1c  mov     eax, ebx
0x18001de1e  jmp     loc_18001DFF2
0x18001de23  mov     rcx, [rsp+68h+arg_18]
0x18001de2b  mov     rax, [rcx]
0x18001de2e  lea     rdx, [rsp+68h+arg_8]
0x18001de33  mov     rax, [rax+50h]
0x18001de37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de3c  mov     ebx, eax
0x18001de3e  cmp     eax, 8004130Bh
0x18001de43  jz      loc_18001DF5D
0x18001de49  test    eax, eax
0x18001de4b  jns     short loc_18001DE9F
0x18001de4d  mov     rcx, [rsp+68h]; this
0x18001de52  mov     r9d, eax; char *
0x18001de55  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001de5c  mov     edx, 0ACh; void *
0x18001de61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001de66  nop
0x18001de67  mov     rcx, [rsp+68h+arg_18]
0x18001de6f  test    rcx, rcx
0x18001de72  jz      short loc_18001DE8D
0x18001de74  mov     [rsp+68h+arg_18], 0
0x18001de80  mov     rax, [rcx]
0x18001de83  mov     rax, [rax+10h]
0x18001de87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de8c  nop
0x18001de8d  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001de92  call    cs:__imp_VariantClear
0x18001de98  mov     eax, ebx
0x18001de9a  jmp     loc_18001DFF2
0x18001de9f  mov     edx, [rsp+68h+arg_8]
0x18001dea3  mov     ecx, edx
0x18001dea5  test    edx, edx
0x18001dea7  jz      short loc_18001DF06
0x18001dea9  sub     ecx, 1
0x18001deac  jz      short loc_18001DECB
0x18001deae  sub     ecx, 1
0x18001deb1  jz      loc_18001DD8E
0x18001deb7  sub     ecx, 1
0x18001deba  jz      loc_18001DD8E
0x18001dec0  cmp     ecx, 1
0x18001dec3  jz      loc_18001DD8E
0x18001dec9  jmp     short loc_18001DF06
0x18001decb  mov     rcx, [rsp+68h+arg_18]
0x18001ded3  test    rcx, rcx
0x18001ded6  jz      short loc_18001DEF1
0x18001ded8  mov     [rsp+68h+arg_18], 0
0x18001dee4  mov     rax, [rcx]
0x18001dee7  mov     rax, [rax+10h]
0x18001deeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001def0  nop
0x18001def1  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001def6  call    cs:__imp_VariantClear
0x18001defc  mov     eax, 41302h
0x18001df01  jmp     loc_18001DFF2
0x18001df06  mov     rcx, [rsp+68h]; this
0x18001df0b  mov     ebx, 8000FFFFh
0x18001df10  mov     r9d, ebx; char *
0x18001df13  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001df1a  mov     edx, 0BCh; void *
0x18001df1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001df24  nop
0x18001df25  mov     rcx, [rsp+68h+arg_18]
0x18001df2d  test    rcx, rcx
0x18001df30  jz      short loc_18001DF4B
0x18001df32  mov     [rsp+68h+arg_18], 0
0x18001df3e  mov     rdx, [rcx]
0x18001df41  mov     rax, [rdx+10h]
0x18001df45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df4a  nop
0x18001df4b  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001df50  call    cs:__imp_VariantClear
0x18001df56  mov     eax, ebx
0x18001df58  jmp     loc_18001DFF2
0x18001df5d  cmp     edi, 0EA60h
0x18001df63  jle     short loc_18001DFB9
0x18001df65  mov     rcx, [rsp+68h]; this
0x18001df6a  mov     ebx, 800705B4h
0x18001df6f  mov     r9d, ebx; char *
0x18001df72  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001df79  mov     edx, 0C1h; void *
0x18001df7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001df83  nop
0x18001df84  mov     rcx, [rsp+68h+arg_18]
0x18001df8c  test    rcx, rcx
0x18001df8f  jz      short loc_18001DFAA
0x18001df91  mov     [rsp+68h+arg_18], 0
0x18001df9d  mov     rdx, [rcx]
0x18001dfa0  mov     rax, [rdx+10h]
0x18001dfa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfa9  nop
0x18001dfaa  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001dfaf  call    cs:__imp_VariantClear
0x18001dfb5  mov     eax, ebx
0x18001dfb7  jmp     short loc_18001DFF2
0x18001dfb9  mov     rcx, [rsp+68h+arg_18]
0x18001dfc1  test    rcx, rcx
0x18001dfc4  jz      short loc_18001DFDF
0x18001dfc6  mov     [rsp+68h+arg_18], 0
0x18001dfd2  mov     rax, [rcx]
0x18001dfd5  mov     rax, [rax+10h]
0x18001dfd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfde  nop
0x18001dfdf  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001dfe4  call    cs:__imp_VariantClear
0x18001dfea  xor     eax, eax
0x18001dfec  jmp     short loc_18001DFF2
0x18001dfee  mov     eax, [rsp+68h+arg_8]
0x18001dff2  lea     r11, [rsp+68h+var_8]
0x18001dff7  mov     rbx, [r11+10h]
0x18001dffb  mov     rsi, [r11+20h]
0x18001dfff  mov     rsp, r11
0x18001e002  pop     rdi
0x18001e003  retn
```
