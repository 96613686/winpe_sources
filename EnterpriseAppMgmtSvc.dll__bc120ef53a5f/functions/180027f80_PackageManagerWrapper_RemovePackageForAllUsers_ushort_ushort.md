# PackageManagerWrapper::RemovePackageForAllUsers(ushort *,ushort *)

- ea: `0x180027f80`
- end: `0x18002812c`
- name: `?RemovePackageForAllUsers@PackageManagerWrapper@@QEAAJPEAG0@Z`
- size: `428`
- prototype: `int(PackageManagerWrapper *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d240`

## callees

- `0x180001c24`
- `0x18000d3dc`
- `0x18001dc30`
- `0x180027f80`
- `0x180030010`
- `0x18006b444`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800280cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800280cf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800280be`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800280be`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002810c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002810c`

## string_xrefs

- `0x180027fa1`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18002807b`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18002808f`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x1800280f3`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PackageManagerWrapper::RemovePackageForAllUsers(
        PackageManagerWrapper *this,
        EnterpriseModernAppManagement *a2,
        unsigned __int16 *a3,
        int *a4)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  __int64 v9; // rdx
  int v10; // edi
  __int64 v11; // rdx
  struct _TP_WORK *ThreadpoolWork; // rax
  signed int LastError; // eax
  const unsigned __int16 **v15; // [rsp+20h] [rbp-18h]
  int v16; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned __int16 *v18; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int16 *Src; // [rsp+48h] [rbp+10h] BYREF
  _DWORD *v20; // [rsp+58h] [rbp+20h]

  v18 = (unsigned __int16 *)this;
  if ( a2 )
  {
    Src = 0;
    LODWORD(v18) = 0;
    v5 = EnterpriseModernAppManagement::ParseRemovePackageParameterString(
           a2,
           (unsigned __int16 *)&Src,
           (const unsigned __int16 **)&v18,
           a4,
           v15);
    if ( (v5 & 0x80000000) != 0 )
    {
      v6 = 1924;
      goto LABEL_3;
    }
    v7 = operator new(0x38u);
    v8 = v7;
    if ( v7 )
    {
      *((_QWORD *)v7 + 2) = 0;
      *((_QWORD *)v7 + 3) = 0;
      *((_QWORD *)v7 + 6) = 0;
      *(_OWORD *)v7 = 0;
      *((_OWORD *)v7 + 2) = 0;
    }
    else
    {
      v8 = 0;
    }
    v20 = v8;
    if ( !v8 )
    {
      v5 = -2147024882;
      v9 = 1927;
      goto LABEL_21;
    }
    v10 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v8, Src);
    if ( v10 >= 0 )
    {
      v8[6] = (_DWORD)v18;
      v10 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)(v8 + 8), a3);
      if ( v10 >= 0 )
      {
        ThreadpoolWork = CreateThreadpoolWork(DoRemovePackageForAllUsers, v8, &g_provisioningCallbackEnvironment);
        if ( ThreadpoolWork )
        {
          SubmitThreadpoolWork(ThreadpoolWork);
          v5 = 0;
          goto LABEL_23;
        }
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( (v5 & 0x80000000) == 0 )
          goto LABEL_23;
        v9 = 1936;
LABEL_21:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v9,
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)v5,
          (int)v15);
LABEL_23:
        Common::AutoPtrDeallocate<RemovePackageForAllUsersParameters>(0);
        return v5;
      }
      v11 = 1832;
    }
    else
    {
      v11 = 1828;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)v10,
      (int)v15);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x788,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)v10,
      v16);
    Common::AutoPtrDeallocate<RemovePackageForAllUsersParameters>(v8);
    return (unsigned int)v10;
  }
  v5 = -2147024809;
  v6 = 1919;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
    (const char *)v5,
    (int)v15);
  return v5;
}

```

## disassembly

```asm
0x180027f80  mov     [rsp+arg_0], rcx
0x180027f85  push    rbx
0x180027f86  push    rsi
0x180027f87  push    rdi; int
0x180027f88  sub     rsp, 20h
0x180027f8c  mov     rsi, r8
0x180027f8f  mov     rax, rdx
0x180027f92  test    rdx, rdx
0x180027f95  jnz     short loc_180027FBA
0x180027f97  mov     ebx, 80070057h
0x180027f9c  mov     edx, 77Fh; void *
0x180027fa1  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180027fa8  mov     r9d, ebx; char *
0x180027fab  mov     rcx, [rsp+38h]; this
0x180027fb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027fb5  jmp     loc_180028121
0x180027fba  mov     [rsp+38h+Src], 0
0x180027fc3  mov     dword ptr [rsp+38h+arg_0], 0
0x180027fcb  lea     r8, [rsp+38h+arg_0]; unsigned __int16 **
0x180027fd0  lea     rdx, [rsp+38h+Src]; unsigned __int16 *
0x180027fd5  mov     rcx, rax; this
0x180027fd8  call    ?ParseRemovePackageParameterString@EnterpriseModernAppManagement@@YAJPEAGPEAPEBGPEAH1@Z; EnterpriseModernAppManagement::ParseRemovePackageParameterString(ushort *,ushort const * *,int *,ushort const * *)
0x180027fdd  mov     ebx, eax
0x180027fdf  test    eax, eax
0x180027fe1  jns     short loc_180027FEA
0x180027fe3  mov     edx, 784h
0x180027fe8  jmp     short loc_180027FA1
0x180027fea  mov     ecx, 38h ; '8'; Size
0x180027fef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027ff4  mov     rbx, rax
0x180027ff7  test    rax, rax
0x180027ffa  jz      short loc_180028020
0x180027ffc  mov     qword ptr [rax+10h], 0
0x180028004  mov     qword ptr [rax+18h], 0
0x18002800c  mov     qword ptr [rax+30h], 0
0x180028014  xorps   xmm0, xmm0
0x180028017  movups  xmmword ptr [rax], xmm0
0x18002801a  movups  xmmword ptr [rax+20h], xmm0
0x18002801e  jmp     short loc_180028022
0x180028020  xor     ebx, ebx
0x180028022  mov     [rsp+38h+arg_18], rbx
0x180028027  test    rbx, rbx
0x18002802a  jnz     short loc_18002803B
0x18002802c  mov     ebx, 8007000Eh
0x180028031  mov     edx, 787h
0x180028036  jmp     loc_1800280F3
0x18002803b  mov     rdx, [rsp+38h+Src]; Src
0x180028040  mov     rcx, rbx; this
0x180028043  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180028048  mov     edi, eax
0x18002804a  test    eax, eax
0x18002804c  jns     short loc_180028055
0x18002804e  mov     edx, 724h
0x180028053  jmp     short loc_180028073
0x180028055  mov     eax, dword ptr [rsp+38h+arg_0]
0x180028059  mov     [rbx+18h], eax
0x18002805c  lea     rcx, [rbx+20h]; this
0x180028060  mov     rdx, rsi; Src
0x180028063  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180028068  mov     edi, eax
0x18002806a  test    eax, eax
0x18002806c  jns     short loc_1800280AD
0x18002806e  mov     edx, 728h; void *
0x180028073  mov     r9d, edi; char *
0x180028076  mov     rcx, [rsp+38h]; this
0x18002807b  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180028082  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028087  mov     rcx, [rsp+38h]; this
0x18002808c  mov     r9d, edi; char *
0x18002808f  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180028096  mov     edx, 788h; void *
0x18002809b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800280a0  nop
0x1800280a1  mov     rcx, rbx
0x1800280a4  call    ??$AutoPtrDeallocate@VRemovePackageForAllUsersParameters@@@Common@@YAXPEAVRemovePackageForAllUsersParameters@@@Z; Common::AutoPtrDeallocate<RemovePackageForAllUsersParameters>(RemovePackageForAllUsersParameters *)
0x1800280a9  mov     eax, edi
0x1800280ab  jmp     short loc_180028123
0x1800280ad  lea     r8, ?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x1800280b4  mov     rdx, rbx; pv
0x1800280b7  lea     rcx, ?DoRemovePackageForAllUsers@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800280be  call    cs:__imp_CreateThreadpoolWork
0x1800280c5  nop     dword ptr [rax+rax+00h]
0x1800280ca  test    rax, rax
0x1800280cd  jnz     short loc_180028109
0x1800280cf  call    cs:__imp_GetLastError
0x1800280d6  nop     dword ptr [rax+rax+00h]
0x1800280db  mov     ebx, eax
0x1800280dd  test    eax, eax
0x1800280df  jle     short loc_1800280EA
0x1800280e1  movzx   ebx, ax
0x1800280e4  or      ebx, 80070000h
0x1800280ea  test    ebx, ebx
0x1800280ec  jns     short loc_18002811A
0x1800280ee  mov     edx, 790h; void *
0x1800280f3  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800280fa  mov     r9d, ebx; char *
0x1800280fd  mov     rcx, [rsp+38h]; this
0x180028102  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028107  jmp     short loc_18002811A
0x180028109  mov     rcx, rax; pwk
0x18002810c  call    cs:__imp_SubmitThreadpoolWork
0x180028113  nop     dword ptr [rax+rax+00h]
0x180028118  xor     ebx, ebx
0x18002811a  xor     ecx, ecx
0x18002811c  call    ??$AutoPtrDeallocate@VRemovePackageForAllUsersParameters@@@Common@@YAXPEAVRemovePackageForAllUsersParameters@@@Z; Common::AutoPtrDeallocate<RemovePackageForAllUsersParameters>(RemovePackageForAllUsersParameters *)
0x180028121  mov     eax, ebx
0x180028123  add     rsp, 20h
0x180028127  pop     rdi
0x180028128  pop     rsi
0x180028129  pop     rbx
0x18002812a  retn
```
