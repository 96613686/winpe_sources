# CPipeInstance::ActivateAPOs(unsigned __int64)

- ea: `0x14000db44`
- end: `0x14000df06`
- name: `?ActivateAPOs@CPipeInstance@@AEAAJ_K@Z`
- size: `962`
- prototype: `__int64 __fastcall(CPipeInstance *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14001a3b0`

## callees

- `0x14000c33c`
- `0x14000db44`
- `0x14000df10`
- `0x14000e11c`
- `0x14000e200`
- `0x14000e280`
- `0x14000f3f8`
- `0x140051d98`
- `0x14005d0e0`
- `0x14005e168`
- `0x140081d08`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x14000dd38`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x14000dd38`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000dd2e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000dd2e`
- `MMDevAPI!__imp_GetClassFromEndpointId` at `0x14000dda6`
- `MMDevAPI!__imp_GetClassFromEndpointId` at `0x14000dda6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000ddd2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000ddd2`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CPipeInstance::ActivateAPOs(CPipeInstance *this, __int64 a2)
{
  __int64 result; // rax
  __int64 v3; // rcx
  __int64 v4; // rdi
  __int64 v5; // rdi
  __int64 v6; // rcx
  int v7; // r13d
  int v8; // r12d
  int v9; // r15d
  int v10; // r14d
  int v11; // esi
  int v12; // edi
  const struct _tlgProvider_t *v13; // rbx
  CPipeInstance *v14; // rbx
  unsigned int v15; // edi
  unsigned int v16; // r15d
  int v17; // r14d
  __int64 v18; // rsi
  HRESULT v19; // ebx
  int ppv; // [rsp+28h] [rbp-E0h]
  unsigned __int8 v21; // [rsp+78h] [rbp-90h]
  unsigned __int8 v22; // [rsp+79h] [rbp-8Fh]
  unsigned __int16 v23; // [rsp+7Ah] [rbp-8Eh]
  unsigned __int16 v24; // [rsp+7Ch] [rbp-8Ch]
  __int64 v25; // [rsp+80h] [rbp-88h] BYREF
  __int64 v26; // [rsp+88h] [rbp-80h] BYREF
  __int64 v27; // [rsp+90h] [rbp-78h] BYREF
  LPVOID v28; // [rsp+98h] [rbp-70h] BYREF
  CPipeInstance *v29; // [rsp+A0h] [rbp-68h]
  __int64 v30; // [rsp+A8h] [rbp-60h]
  _QWORD v31[5]; // [rsp+B0h] [rbp-58h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v33; // [rsp+E0h] [rbp-28h]
  LARGE_INTEGER Frequency; // [rsp+E8h] [rbp-20h] BYREF
  char pszDest[64]; // [rsp+F0h] [rbp-18h] BYREF
  char v36[128]; // [rsp+130h] [rbp+28h] BYREF
  STRSAFE_LPSTR v37; // [rsp+1B0h] [rbp+A8h] BYREF
  size_t cbDest[2]; // [rsp+1B8h] [rbp+B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+220h] [rbp+118h]
  __int64 v40; // [rsp+230h] [rbp+128h] BYREF

  v40 = a2;
  v29 = this;
  for ( result = *((_QWORD *)this + 3); result; result = v3 )
  {
    v3 = *(_QWORD *)(result + 8);
    v30 = v3;
    v4 = *(_QWORD *)(result + 16);
    if ( *(_DWORD *)(v4 + 40) == 2 )
    {
      v5 = *(_QWORD *)(v4 + 32);
      v27 = v5;
      v26 = 0;
      v26 = *(_QWORD *)(v5 + 40);
      v6 = *(_QWORD *)(v5 + 40);
      if ( v6 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
        v5 = v27;
      }
      LODWORD(v25) = *(_DWORD *)(v5 + 8);
      v24 = *(_WORD *)(v5 + 12);
      v23 = *(_WORD *)(v5 + 14);
      v22 = *(_BYTE *)(v5 + 16);
      v21 = *(_BYTE *)(v5 + 17);
      v7 = *(unsigned __int8 *)(v5 + 18);
      v8 = *(unsigned __int8 *)(v5 + 19);
      v9 = *(unsigned __int8 *)(v5 + 20);
      v10 = *(unsigned __int8 *)(v5 + 21);
      v11 = *(unsigned __int8 *)(v5 + 22);
      v12 = *(unsigned __int8 *)(v5 + 23);
      v13 = AudioDgTelemetryProvider::Provider();
      PerformanceCount.QuadPart = 0;
      v33 = 0;
      Frequency.QuadPart = 0;
      memset_0(pszDest, 0, sizeof(pszDest));
      memset_0(v36, 0, sizeof(v36));
      cbDest[1] = (size_t)v13;
      StringCchPrintfExA(pszDest, 0x40u, &v37, cbDest, 0, "%s", "ActivateApo");
      StringCchPrintfExA(v37, cbDest[0], 0, 0, 0, "-Start");
      StringCchPrintfA(
        v36,
        0x80u,
        "{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
        v25,
        v24,
        v23,
        v22,
        v21,
        v7,
        v8,
        v9,
        v10,
        v11,
        v12);
      QueryPerformanceCounter(&PerformanceCount);
      QueryPerformanceFrequency(&Frequency);
      v14 = v29;
      v31[0] = v29;
      v31[1] = &v40;
      v31[2] = &v26;
      v31[3] = &v27;
      v15 = lambda_500db2d6cfbf3b8fca54c06eac8d2ece_::operator()(v31);
      CPerfTracker::~CPerfTracker((CPerfTracker *)&PerformanceCount);
      v16 = *(_DWORD *)(v27 + 4);
      if ( v16 )
      {
        v17 = v27 + 8;
        v18 = *((_QWORD *)v14 + 24);
        v28 = 0;
        v25 = 0;
        if ( (unsigned int)GetClassFromEndpointId(v18) == 3 )
        {
          v19 = 0;
        }
        else
        {
          v19 = CoCreateInstance(
                  &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
                  0,
                  0x17u,
                  &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
                  &v28);
          if ( v19 >= 0 )
          {
            v19 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v28 + 40LL))(v28, v18, &v25);
            if ( v19 >= 0 )
            {
              ppv = v17;
              v19 = TrackSystemEffectBehavior(v25, v16, v15, 0);
            }
          }
        }
        if ( v25 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        if ( v28 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
        if ( v19 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xC46,
            (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\pipeinstance.cpp",
            (const char *)(unsigned int)v19,
            ppv);
      }
      if ( (v15 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC48,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\pipeinstance.cpp",
          (const char *)v15,
          ppv);
        if ( v26 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        return v15;
      }
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      v3 = v30;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000db44  mov     rax, rsp
0x14000db47  mov     [rax+18h], rbx
0x14000db4b  mov     [rax+10h], rdx
0x14000db4f  push    rbp
0x14000db50  push    rsi
0x14000db51  push    rdi
0x14000db52  push    r12
0x14000db54  push    r13
0x14000db56  push    r14
0x14000db58  push    r15
0x14000db5a  lea     rbp, [rax-118h]
0x14000db61  sub     rsp, 1E0h
0x14000db68  movaps  xmmword ptr [rax-48h], xmm6
0x14000db6c  mov     rax, cs:__security_cookie
0x14000db73  xor     rax, rsp
0x14000db76  mov     [rbp+110h+var_50], rax
0x14000db7d  mov     [rbp+110h+var_178], rcx
0x14000db81  mov     rax, [rcx+18h]
0x14000db85  movss   xmm6, cs:__real@3f800000
0x14000db8d  test    rax, rax
0x14000db90  jz      loc_14000DE88
0x14000db96  mov     rcx, [rax+8]
0x14000db9a  mov     [rbp+110h+var_170], rcx
0x14000db9e  mov     rdi, [rax+10h]
0x14000dba2  cmp     dword ptr [rdi+28h], 2
0x14000dba6  jnz     loc_14000DE4C
0x14000dbac  mov     rdi, [rdi+20h]
0x14000dbb0  mov     [rbp+110h+var_188], rdi
0x14000dbb4  mov     [rbp+110h+var_190], 0
0x14000dbbc  mov     rax, [rdi+28h]
0x14000dbc0  mov     [rbp+110h+var_190], rax
0x14000dbc4  mov     rcx, [rdi+28h]
0x14000dbc8  test    rcx, rcx
0x14000dbcb  jz      short loc_14000DBDD
0x14000dbcd  mov     rax, [rcx]
0x14000dbd0  mov     rax, [rax+8]
0x14000dbd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dbd9  mov     rdi, [rbp+110h+var_188]
0x14000dbdd  mov     eax, [rdi+8]
0x14000dbe0  mov     dword ptr [rsp+210h+var_198], eax
0x14000dbe4  movzx   eax, word ptr [rdi+0Ch]
0x14000dbe8  mov     word ptr [rsp+210h+var_1A0+4], ax
0x14000dbed  movzx   eax, word ptr [rdi+0Eh]
0x14000dbf1  mov     word ptr [rsp+210h+var_1A0+2], ax
0x14000dbf6  mov     al, [rdi+10h]
0x14000dbf9  mov     byte ptr [rsp+210h+var_1A0+1], al
0x14000dbfd  mov     al, [rdi+11h]
0x14000dc00  mov     byte ptr [rsp+210h+var_1A0], al
0x14000dc04  movzx   r13d, byte ptr [rdi+12h]
0x14000dc09  movzx   r12d, byte ptr [rdi+13h]
0x14000dc0e  movzx   r15d, byte ptr [rdi+14h]
0x14000dc13  movzx   r14d, byte ptr [rdi+15h]
0x14000dc18  movzx   esi, byte ptr [rdi+16h]
0x14000dc1c  movzx   edi, byte ptr [rdi+17h]
0x14000dc20  call    ?Provider@AudioDgTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioDgTelemetryProvider::Provider(void)
0x14000dc25  mov     rbx, rax
0x14000dc28  xor     eax, eax
0x14000dc2a  mov     qword ptr [rbp+110h+PerformanceCount], rax
0x14000dc2e  mov     [rbp+110h+var_138], rax
0x14000dc32  mov     qword ptr [rbp+110h+Frequency], rax
0x14000dc36  xor     edx, edx; Val
0x14000dc38  lea     r8d, [rax+40h]; Size
0x14000dc3c  lea     rcx, [rbp+110h+pszDest]; void *
0x14000dc40  call    memset_0
0x14000dc45  xor     edx, edx; Val
0x14000dc47  mov     r8d, 80h; Size
0x14000dc4d  lea     rcx, [rbp+110h+var_E8]; void *
0x14000dc51  call    memset_0
0x14000dc56  mov     [rbp+110h+var_58], rbx
0x14000dc5d  lea     rax, aActivateapo; "ActivateApo"
0x14000dc64  mov     qword ptr [rsp+210h+var_1E0], rax
0x14000dc69  lea     rax, aS; "%s"
0x14000dc70  mov     [rsp+210h+var_1E8], rax; char *
0x14000dc75  mov     [rsp+210h+ppv], 0; DWORD
0x14000dc7e  lea     r9, [rbp+110h+cbDest]; unsigned __int64 *
0x14000dc85  lea     r8, [rbp+110h+var_68]; char **
0x14000dc8c  mov     edx, 40h ; '@'; cbDest
0x14000dc91  lea     rcx, [rbp+110h+pszDest]; pszDest
0x14000dc95  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x14000dc9a  lea     rax, aStart; "-Start"
0x14000dca1  mov     [rsp+210h+var_1E8], rax; char *
0x14000dca6  mov     [rsp+210h+ppv], 0; DWORD
0x14000dcaf  xor     r9d, r9d; unsigned __int64 *
0x14000dcb2  xor     r8d, r8d; char **
0x14000dcb5  mov     rdx, [rbp+110h+cbDest]; cbDest
0x14000dcbc  mov     rcx, [rbp+110h+var_68]; pszDest
0x14000dcc3  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x14000dcc8  mov     eax, edi
0x14000dcca  mov     ecx, esi
0x14000dccc  mov     edx, r14d
0x14000dccf  movzx   ebx, byte ptr [rsp+210h+var_1A0]
0x14000dcd4  movzx   edi, byte ptr [rsp+210h+var_1A0+1]
0x14000dcd9  movzx   esi, word ptr [rsp+210h+var_1A0+2]
0x14000dcde  movzx   r14d, word ptr [rsp+210h+var_1A0+4]
0x14000dce4  mov     dword ptr [rsp+210h+var_1A8], eax
0x14000dce8  mov     [rsp+210h+var_1B0], ecx
0x14000dcec  mov     [rsp+210h+var_1B8], edx
0x14000dcf0  mov     [rsp+210h+var_1C0], r15d
0x14000dcf5  mov     [rsp+210h+var_1C8], r12d
0x14000dcfa  mov     [rsp+210h+var_1D0], r13d
0x14000dcff  mov     [rsp+210h+var_1D8], ebx
0x14000dd03  mov     [rsp+210h+var_1E0], edi
0x14000dd07  mov     dword ptr [rsp+210h+var_1E8], esi
0x14000dd0b  mov     dword ptr [rsp+210h+ppv], r14d
0x14000dd10  mov     r9d, dword ptr [rsp+210h+var_198]
0x14000dd15  lea     r8, a08x04x04x02x02; "{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%0"...
0x14000dd1c  mov     edx, 80h; unsigned __int64
0x14000dd21  lea     rcx, [rbp+110h+var_E8]; char *
0x14000dd25  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x14000dd2a  lea     rcx, [rbp+110h+PerformanceCount]; lpPerformanceCount
0x14000dd2e  call    cs:__imp_QueryPerformanceCounter
0x14000dd34  lea     rcx, [rbp+110h+Frequency]; lpFrequency
0x14000dd38  call    cs:__imp_QueryPerformanceFrequency
0x14000dd3e  nop
0x14000dd3f  mov     rbx, [rbp+110h+var_178]
0x14000dd43  mov     [rbp+110h+var_168], rbx
0x14000dd47  lea     rax, [rbp+110h+arg_8]
0x14000dd4e  mov     [rbp+110h+var_160], rax
0x14000dd52  lea     rax, [rbp+110h+var_190]
0x14000dd56  mov     [rbp+110h+var_158], rax
0x14000dd5a  lea     rax, [rbp+110h+var_188]
0x14000dd5e  mov     [rbp+110h+var_150], rax
0x14000dd62  lea     rcx, [rbp+110h+var_168]
0x14000dd66  call    _lambda_500db2d6cfbf3b8fca54c06eac8d2ece___operator__
0x14000dd6b  mov     edi, eax
0x14000dd6d  lea     rcx, [rbp+110h+PerformanceCount]; this
0x14000dd71  call    ??1CPerfTracker@@QEAA@XZ; CPerfTracker::~CPerfTracker(void)
0x14000dd76  mov     r14, [rbp+110h+var_188]
0x14000dd7a  mov     r15d, [r14+4]
0x14000dd7e  test    r15d, r15d
0x14000dd81  jz      loc_14000DE2E
0x14000dd87  add     r14, 8
0x14000dd8b  mov     rsi, [rbx+0C0h]
0x14000dd92  mov     [rbp+110h+var_180], 0
0x14000dd9a  mov     [rsp+210h+var_198], 0
0x14000dda3  mov     rcx, rsi
0x14000dda6  call    cs:__imp_GetClassFromEndpointId
0x14000ddac  cmp     eax, 3
0x14000ddaf  jz      loc_14000DEB7
0x14000ddb5  lea     rax, [rbp+110h+var_180]
0x14000ddb9  mov     [rsp+210h+ppv], rax; int
0x14000ddbe  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x14000ddc5  xor     edx, edx; pUnkOuter
0x14000ddc7  lea     r8d, [rdx+17h]; dwClsContext
0x14000ddcb  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x14000ddd2  call    cs:__imp_CoCreateInstance
0x14000ddd8  mov     ebx, eax
0x14000ddda  test    eax, eax
0x14000dddc  jns     loc_14000DEBE
0x14000dde2  mov     rcx, [rsp+210h+var_198]
0x14000dde7  test    rcx, rcx
0x14000ddea  jz      short loc_14000DDF9
0x14000ddec  mov     rax, [rcx]
0x14000ddef  mov     rax, [rax+10h]
0x14000ddf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ddf8  nop
0x14000ddf9  mov     rcx, [rbp+110h+var_180]
0x14000ddfd  test    rcx, rcx
0x14000de00  jz      short loc_14000DE0F
0x14000de02  mov     rax, [rcx]
0x14000de05  mov     rax, [rax+10h]
0x14000de09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000de0e  nop
0x14000de0f  mov     rcx, [rbp+118h]; this
0x14000de16  test    ebx, ebx
0x14000de18  jns     short loc_14000DE2E
0x14000de1a  mov     r9d, ebx; char *
0x14000de1d  lea     r8, aAvcoreAudiocor_76; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14000de24  mov     edx, 0C46h; void *
0x14000de29  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000de2e  test    edi, edi
0x14000de30  js      short loc_14000DE54
0x14000de32  mov     rcx, [rbp+110h+var_190]
0x14000de36  test    rcx, rcx
0x14000de39  jz      short loc_14000DE48
0x14000de3b  mov     rax, [rcx]
0x14000de3e  mov     rax, [rax+10h]
0x14000de42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000de47  nop
0x14000de48  mov     rcx, [rbp+110h+var_170]
0x14000de4c  mov     rax, rcx
0x14000de4f  jmp     loc_14000DB8D
0x14000de54  mov     rcx, [rbp+118h]; this
0x14000de5b  mov     r9d, edi; char *
0x14000de5e  lea     r8, aAvcoreAudiocor_76; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14000de65  mov     edx, 0C48h; void *
0x14000de6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000de6f  nop
0x14000de70  mov     rcx, [rbp+110h+var_190]
0x14000de74  test    rcx, rcx
0x14000de77  jz      short loc_14000DE86
0x14000de79  mov     rax, [rcx]
0x14000de7c  mov     rax, [rax+10h]
0x14000de80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000de85  nop
0x14000de86  mov     eax, edi
0x14000de88  mov     rcx, [rbp+110h+var_50]
0x14000de8f  xor     rcx, rsp; StackCookie
0x14000de92  call    __security_check_cookie
0x14000de97  lea     r11, [rsp+210h+var_30]
0x14000de9f  mov     rbx, [r11+50h]
0x14000dea3  movaps  xmm6, xmmword ptr [r11-10h]
0x14000dea8  mov     rsp, r11
0x14000deab  pop     r15
0x14000dead  pop     r14
0x14000deaf  pop     r13
0x14000deb1  pop     r12
0x14000deb3  pop     rdi
0x14000deb4  pop     rsi
0x14000deb5  pop     rbp
0x14000deb6  retn
0x14000deb7  xor     ebx, ebx
0x14000deb9  jmp     loc_14000DDE2
0x14000debe  mov     rcx, [rbp+110h+var_180]
0x14000dec2  mov     rax, [rcx]
0x14000dec5  lea     r8, [rsp+210h+var_198]
0x14000deca  mov     rdx, rsi
0x14000decd  mov     rax, [rax+28h]
0x14000ded1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ded6  mov     ebx, eax
0x14000ded8  test    eax, eax
0x14000deda  js      loc_14000DDE2
0x14000dee0  movss   dword ptr [rsp+210h+var_1E8], xmm6
0x14000dee6  mov     [rsp+210h+ppv], r14
0x14000deeb  xor     r9d, r9d
0x14000deee  mov     r8d, edi
0x14000def1  mov     edx, r15d
0x14000def4  mov     rcx, [rsp+210h+var_198]
0x14000def9  call    ?TrackSystemEffectBehavior@@YAJPEAUIMMDevice@@W4__MIDL___MIDL_itf_audioenginepolicy_0000_0009_0003@@J_NAEBU_GUID@@M@Z; TrackSystemEffectBehavior(IMMDevice *,__MIDL___MIDL_itf_audioenginepolicy_0000_0009_0003,long,bool,_GUID const &,float)
0x14000defe  mov     ebx, eax
0x14000df00  jmp     loc_14000DDE2
```
