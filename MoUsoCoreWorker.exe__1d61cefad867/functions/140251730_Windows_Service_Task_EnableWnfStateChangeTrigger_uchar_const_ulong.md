# Windows::Service::Task::EnableWnfStateChangeTrigger(uchar const *,ulong)

- ea: `0x140251730`
- end: `0x140251a51`
- name: `?EnableWnfStateChangeTrigger@Task@Service@Windows@@QEAAXPEBEK@Z`
- size: `801`
- prototype: `void(Windows::Service::Task *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1402533d0`

## callees

- `0x1400413a8`
- `0x140251730`
- `0x140379070`
- `0x140380b50`
- `0x1403816b0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x140251845`
- `OLEAUT32!__imp_VariantInit` at `0x140251845`
- `OLEAUT32!__imp_VariantClear` at `0x14025189e`
- `OLEAUT32!__imp_VariantClear` at `0x140251971`
- `OLEAUT32!__imp_VariantClear` at `0x14025189e`
- `OLEAUT32!__imp_VariantClear` at `0x140251971`

## string_xrefs

- `0x140251a3f`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x1402519ac`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x1402519c1`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x1402519d6`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x1402519eb`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x140251a00`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x140251a15`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x140251a2a`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Windows::Service::Task::EnableWnfStateChangeTrigger(
        Windows::Service::Task *this,
        const unsigned __int8 *a2,
        unsigned int a3)
{
  size_t v3; // rdi
  int v6; // eax
  int v7; // eax
  int i; // ebx
  __int64 v9; // rax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  VARIANTARG pvarg; // [rsp+20h] [rbp-50h] BYREF
  __int16 v17; // [rsp+38h] [rbp-38h] BYREF
  __int64 v18; // [rsp+40h] [rbp-30h] BYREF
  int v19; // [rsp+48h] [rbp-28h] BYREF
  int v20; // [rsp+4Ch] [rbp-24h] BYREF
  __int64 *v21; // [rsp+50h] [rbp-20h] BYREF
  __int64 v22; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v3 = a3;
  v21 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(**(_QWORD **)this + 72LL))(*(_QWORD *)this, &v21);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13C,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v6,
      *(int *)&pvarg.vt);
  v19 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v21 + 56))(v21, &v19);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13F,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v7,
      *(int *)&pvarg.vt);
  for ( i = 1; i <= v19; ++i )
  {
    v18 = 0;
    v9 = *v21;
    v18 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v9 + 64))(v21, (unsigned int)i, &v18);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x144,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v10,
        *(int *)&pvarg.vt);
    v20 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 56LL))(v18, &v20);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x147,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v11,
        *(int *)&pvarg.vt);
    if ( v20 == 12 )
    {
      v22 = 0;
      v12 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v18)(
              v18,
              &GUID_2d92bf38_0538_477b_b4d4_6c8e1dc9484f,
              &v22);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1C96,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v12,
          *(int *)&pvarg.vt);
      VariantInit(&pvarg);
      pvarg.vt = 27;
      v13 = (*(__int64 (__fastcall **)(__int64, CY *))(*(_QWORD *)v22 + 176LL))(v22, &pvarg.cyVal);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x14E,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
          (const char *)(unsigned int)v13,
          *(int *)&pvarg.vt);
      if ( *pvarg.bstrVal == 1
        && *(_DWORD *)(pvarg.llVal + 24) == (_DWORD)v3
        && !memcmp(a2, *(const void **)(pvarg.llVal + 16), v3) )
      {
        v17 = 0;
        v14 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v18 + 144LL))(v18, &v17);
        if ( v14 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x154,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
            (const char *)(unsigned int)v14,
            *(int *)&pvarg.vt);
        if ( !v17 )
        {
          v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 152LL))(v18, 0xFFFFFFFFLL);
          if ( v15 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x157,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
              (const char *)(unsigned int)v15,
              *(int *)&pvarg.vt);
          *((_BYTE *)this + 40) = 1;
        }
        VariantClear(&pvarg);
        if ( v22 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        break;
      }
      VariantClear(&pvarg);
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  if ( v21 )
    (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
}

```

## disassembly

```asm
0x140251730  mov     [rsp-28h+arg_8], rbx
0x140251735  mov     [rsp-28h+arg_10], rsi
0x14025173a  push    rbp
0x14025173b  push    rdi
0x14025173c  push    r12
0x14025173e  push    r14
0x140251740  push    r15
0x140251742  mov     rbp, rsp
0x140251745  sub     rsp, 70h
0x140251749  mov     rax, cs:__security_cookie
0x140251750  xor     rax, rsp
0x140251753  mov     [rbp+var_10], rax
0x140251757  mov     edi, r8d
0x14025175a  mov     r14, rdx
0x14025175d  mov     rsi, rcx
0x140251760  xor     r15d, r15d
0x140251763  mov     [rbp+var_20], r15
0x140251767  mov     rcx, [rcx]
0x14025176a  mov     rax, [rcx]
0x14025176d  mov     [rbp+var_20], r15
0x140251771  lea     rdx, [rbp+var_20]
0x140251775  mov     rax, [rax+48h]
0x140251779  call    _guard_dispatch_icall
0x14025177e  mov     rcx, [rbp+28h]; this
0x140251782  test    eax, eax
0x140251784  js      loc_1402519D3
0x14025178a  mov     [rbp+var_28], r15d
0x14025178e  mov     rcx, [rbp+var_20]
0x140251792  mov     rax, [rcx]
0x140251795  lea     rdx, [rbp+var_28]
0x140251799  mov     rax, [rax+38h]
0x14025179d  call    _guard_dispatch_icall
0x1402517a2  mov     rcx, [rbp+28h]; this
0x1402517a6  test    eax, eax
0x1402517a8  js      loc_1402519E8
0x1402517ae  lea     r12d, [r15+1]
0x1402517b2  mov     ebx, r12d
0x1402517b5  cmp     [rbp+var_28], r12d
0x1402517b9  jl      loc_1402518DD
0x1402517bf  mov     [rbp+var_30], r15
0x1402517c3  mov     rcx, [rbp+var_20]
0x1402517c7  mov     rax, [rcx]
0x1402517ca  mov     [rbp+var_30], r15
0x1402517ce  lea     r8, [rbp+var_30]
0x1402517d2  mov     edx, ebx
0x1402517d4  mov     rax, [rax+40h]
0x1402517d8  call    _guard_dispatch_icall
0x1402517dd  mov     rcx, [rbp+28h]; this
0x1402517e1  test    eax, eax
0x1402517e3  js      loc_1402519BE
0x1402517e9  mov     [rbp+var_24], r15d
0x1402517ed  mov     rcx, [rbp+var_30]
0x1402517f1  mov     rax, [rcx]
0x1402517f4  lea     rdx, [rbp+var_24]
0x1402517f8  mov     rax, [rax+38h]
0x1402517fc  call    _guard_dispatch_icall
0x140251801  mov     rcx, [rbp+28h]; this
0x140251805  test    eax, eax
0x140251807  js      loc_1402519A9
0x14025180d  cmp     [rbp+var_24], 0Ch
0x140251811  jnz     loc_1402518BB
0x140251817  mov     rcx, [rbp+var_30]
0x14025181b  mov     [rbp+var_18], r15
0x14025181f  mov     rax, [rcx]
0x140251822  lea     r8, [rbp+var_18]
0x140251826  lea     rdx, _GUID_2d92bf38_0538_477b_b4d4_6c8e1dc9484f
0x14025182d  mov     rax, [rax]
0x140251830  call    _guard_dispatch_icall
0x140251835  mov     rcx, [rbp+28h]; this
0x140251839  test    eax, eax
0x14025183b  js      loc_140251A3C
0x140251841  lea     rcx, [rbp+pvarg]; pvarg
0x140251845  call    cs:__imp_VariantInit
0x14025184b  nop
0x14025184c  mov     eax, 1Bh
0x140251851  mov     word ptr [rbp+pvarg], ax
0x140251855  mov     rcx, [rbp+var_18]
0x140251859  mov     rax, [rcx]
0x14025185c  lea     rdx, [rbp+pvarg+8]
0x140251860  mov     rax, [rax+0B0h]
0x140251867  call    _guard_dispatch_icall
0x14025186c  mov     rcx, [rbp+28h]; this
0x140251870  test    eax, eax
0x140251872  js      loc_140251A27
0x140251878  mov     rdx, qword ptr [rbp+pvarg+8]
0x14025187c  cmp     [rdx], r12w
0x140251880  jnz     short loc_14025189A
0x140251882  cmp     [rdx+18h], edi
0x140251885  jnz     short loc_14025189A
0x140251887  mov     r8, rdi; Size
0x14025188a  mov     rdx, [rdx+10h]; Buf2
0x14025188e  mov     rcx, r14; Buf1
0x140251891  call    memcmp
0x140251896  test    eax, eax
0x140251898  jz      short loc_140251918
0x14025189a  lea     rcx, [rbp+pvarg]; pvarg
0x14025189e  call    cs:__imp_VariantClear
0x1402518a4  nop
0x1402518a5  mov     rcx, [rbp+var_18]
0x1402518a9  test    rcx, rcx
0x1402518ac  jz      short loc_1402518BB
0x1402518ae  mov     rax, [rcx]
0x1402518b1  mov     rax, [rax+10h]
0x1402518b5  call    _guard_dispatch_icall
0x1402518ba  nop
0x1402518bb  mov     rcx, [rbp+var_30]
0x1402518bf  test    rcx, rcx
0x1402518c2  jz      short loc_1402518D1
0x1402518c4  mov     rax, [rcx]
0x1402518c7  mov     rax, [rax+10h]
0x1402518cb  call    _guard_dispatch_icall
0x1402518d0  nop
0x1402518d1  add     ebx, r12d
0x1402518d4  cmp     ebx, [rbp+var_28]
0x1402518d7  jle     loc_1402517BF
0x1402518dd  mov     rcx, [rbp+var_20]
0x1402518e1  test    rcx, rcx
0x1402518e4  jz      short loc_1402518F3
0x1402518e6  mov     rax, [rcx]
0x1402518e9  mov     rax, [rax+10h]
0x1402518ed  call    _guard_dispatch_icall
0x1402518f2  nop
0x1402518f3  mov     rcx, [rbp+var_10]
0x1402518f7  xor     rcx, rsp; StackCookie
0x1402518fa  call    __security_check_cookie
0x1402518ff  lea     r11, [rsp+70h+var_s0]
0x140251904  mov     rbx, [r11+38h]
0x140251908  mov     rsi, [r11+40h]
0x14025190c  mov     rsp, r11
0x14025190f  pop     r15
0x140251911  pop     r14
0x140251913  pop     r12
0x140251915  pop     rdi
0x140251916  pop     rbp
0x140251917  retn
0x140251918  mov     [rbp+var_38], r15w
0x14025191d  mov     rcx, [rbp+var_30]
0x140251921  mov     rax, [rcx]
0x140251924  lea     rdx, [rbp+var_38]
0x140251928  mov     rax, [rax+90h]
0x14025192f  call    _guard_dispatch_icall
0x140251934  mov     rcx, [rbp+28h]; this
0x140251938  test    eax, eax
0x14025193a  js      loc_1402519FD
0x140251940  cmp     [rbp+var_38], r15w
0x140251945  jnz     short loc_14025196D
0x140251947  or      edx, 0FFFFFFFFh
0x14025194a  mov     rcx, [rbp+var_30]
0x14025194e  mov     rax, [rcx]
0x140251951  mov     rax, [rax+98h]
0x140251958  call    _guard_dispatch_icall
0x14025195d  mov     rcx, [rbp+28h]; this
0x140251961  test    eax, eax
0x140251963  js      loc_140251A12
0x140251969  mov     [rsi+28h], r12b
0x14025196d  lea     rcx, [rbp+pvarg]; pvarg
0x140251971  call    cs:__imp_VariantClear
0x140251977  nop
0x140251978  mov     rcx, [rbp+var_18]
0x14025197c  test    rcx, rcx
0x14025197f  jz      short loc_14025198E
0x140251981  mov     rax, [rcx]
0x140251984  mov     rax, [rax+10h]
0x140251988  call    _guard_dispatch_icall
0x14025198d  nop
0x14025198e  mov     rcx, [rbp+var_30]
0x140251992  test    rcx, rcx
0x140251995  jz      short loc_1402519A4
0x140251997  mov     rax, [rcx]
0x14025199a  mov     rax, [rax+10h]
0x14025199e  call    _guard_dispatch_icall
0x1402519a3  nop
0x1402519a4  jmp     loc_1402518DD
0x1402519a9  mov     r9d, eax; char *
0x1402519ac  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402519b3  mov     edx, 147h; void *
0x1402519b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402519be  mov     r9d, eax; char *
0x1402519c1  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402519c8  mov     edx, 144h; void *
0x1402519cd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402519d3  mov     r9d, eax; char *
0x1402519d6  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402519dd  mov     edx, 13Ch; void *
0x1402519e2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402519e8  mov     r9d, eax; char *
0x1402519eb  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402519f2  mov     edx, 13Fh; void *
0x1402519f7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402519fd  mov     r9d, eax; char *
0x140251a00  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140251a07  mov     edx, 154h; void *
0x140251a0c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140251a12  mov     r9d, eax; char *
0x140251a15  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140251a1c  mov     edx, 157h; void *
0x140251a21  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140251a27  mov     r9d, eax; char *
0x140251a2a  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140251a31  mov     edx, 14Eh; void *
0x140251a36  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140251a3c  mov     r9d, eax; char *
0x140251a3f  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140251a46  mov     edx, 1C96h; void *
0x140251a4b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
