# WindowsUpdateAdministration::RequestRestart(wchar_t const *,wchar_t * *)

- ea: `0x180041040`
- end: `0x18004133b`
- name: `?RequestRestart@WindowsUpdateAdministration@@UEAAJPEB_WPEAPEA_W@Z`
- size: `763`
- prototype: `__int64 __fastcall(WindowsUpdateAdministration *__hidden this, const wchar_t *, wchar_t **)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180008e64`
- `0x1800108b4`
- `0x180011680`
- `0x18002e698`
- `0x180032028`
- `0x180040a08`
- `0x180041040`
- `0x180041480`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180041140`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180041140`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180041197`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180041197`

## string_xrefs

- `0x180041080`: `C:\__w\1\s\src\orchestrator\core\USOSvc\WindowsUpdateAdministrationImpl.cpp`
- `0x1800410c4`: `C:\__w\1\s\src\orchestrator\core\USOSvc\WindowsUpdateAdministrationImpl.cpp`
- `0x180041103`: `C:\__w\1\s\src\orchestrator\core\USOSvc\WindowsUpdateAdministrationImpl.cpp`
- `0x180041157`: `C:\__w\1\s\src\orchestrator\core\USOSvc\WindowsUpdateAdministrationImpl.cpp`
- `0x1800411b1`: `C:\__w\1\s\src\orchestrator\core\USOSvc\WindowsUpdateAdministrationImpl.cpp`
- `0x180041262`: `C:\__w\1\s\src\orchestrator\core\USOSvc\WindowsUpdateAdministrationImpl.cpp`
- `0x1800412fd`: `C:\__w\1\s\src\orchestrator\core\USOSvc\WindowsUpdateAdministrationImpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WindowsUpdateAdministration::RequestRestart(
        WindowsUpdateAdministration *this,
        const wchar_t *a2,
        wchar_t **a3)
{
  int CoreWorker; // eax
  unsigned int v7; // ebx
  HRESULT v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // r8
  __int128 *p_Src; // rdx
  int v12; // eax
  unsigned int v13; // ebx
  __int128 *v14; // rdx
  wchar_t *v15; // rax
  void *v16; // [rsp+20h] [rbp-B8h] BYREF
  wchar_t *v17; // [rsp+28h] [rbp-B0h] BYREF
  __int128 Src; // [rsp+30h] [rbp-A8h] BYREF
  __int128 v19; // [rsp+40h] [rbp-98h]
  GUID pguid; // [rsp+50h] [rbp-88h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  if ( a3 )
  {
    if ( a2 && *a2 )
    {
      if ( IsSystemOrAdmin() )
      {
        v16 = 0;
        CoreWorker = GetCoreWorker(&GUID_af2ba583_e24f_43f1_b92b_fc8125f93d16, &v16);
        v7 = CoreWorker;
        if ( CoreWorker >= 0 )
        {
          pguid = 0;
          v8 = CoCreateGuid(&pguid);
          v9 = v8;
          if ( v8 >= 0 )
          {
            if ( StringFromGUID2(&pguid, sz, 40) )
            {
              Src = 0;
              v19 = 0;
              std::wstring::_Construct<1,wchar_t const *>(&Src);
              v10 = -1;
              do
                ++v10;
              while ( sz[v10] );
              std::wstring::append(&Src);
              p_Src = &Src;
              if ( *((_QWORD *)&v19 + 1) > 7u )
                p_Src = (__int128 *)Src;
              v12 = (*(__int64 (__fastcall **)(void *, __int128 *, const wchar_t *))(*(_QWORD *)v16 + 96LL))(
                      v16,
                      p_Src,
                      a2);
              v13 = v12;
              if ( v12 >= 0 )
              {
                v17 = 0;
                v14 = &Src;
                if ( *((_QWORD *)&v19 + 1) > 7u )
                  v14 = (__int128 *)Src;
                wil::make_bstr(&v17, v14);
                v15 = v17;
                v17 = 0;
                *a3 = v15;
                std::wstring::~wstring(&Src);
                if ( v16 )
                  (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
                return 0;
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x103,
                  (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\WindowsUpdateAdministrationImpl.cpp",
                  (const char *)(unsigned int)v12,
                  (int)v16);
                std::wstring::~wstring(&Src);
                if ( v16 )
                  (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
                return v13;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xFF,
                (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\WindowsUpdateAdministrationImpl.cpp",
                (const char *)0x8007007ALL,
                (int)v16);
              if ( v16 )
                (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)v16 + 16LL))(v16, *(_QWORD *)v16);
              return 2147942522LL;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xFE,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\WindowsUpdateAdministrationImpl.cpp",
              (const char *)(unsigned int)v8,
              (int)v16);
            if ( v16 )
              (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
            return v9;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xFA,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\WindowsUpdateAdministrationImpl.cpp",
            (const char *)(unsigned int)CoreWorker,
            (int)v16);
          if ( v16 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
          return v7;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF7,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\WindowsUpdateAdministrationImpl.cpp",
          (const char *)0x80070005LL,
          (int)v16);
        return 2147942405LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF4,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\WindowsUpdateAdministrationImpl.cpp",
        (const char *)0x80070057LL,
        (int)v16);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF3,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\WindowsUpdateAdministrationImpl.cpp",
      (const char *)0x80070057LL,
      (int)v16);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180041040  mov     [rsp+arg_0], rbx
0x180041045  push    rsi
0x180041046  push    rdi
0x180041047  push    r14
0x180041049  sub     rsp, 0C0h
0x180041050  mov     rax, cs:__security_cookie
0x180041057  xor     rax, rsp
0x18004105a  mov     [rsp+0D8h+var_28], rax
0x180041062  mov     rsi, r8
0x180041065  mov     rdi, rdx
0x180041068  xor     r14d, r14d
0x18004106b  test    r8, r8
0x18004106e  jnz     short loc_180041098
0x180041070  mov     rcx, [rsp+0D8h]; this
0x180041078  mov     ebx, 80070057h
0x18004107d  mov     r9d, ebx; char *
0x180041080  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180041087  mov     edx, 0F3h; void *
0x18004108c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041091  mov     eax, ebx
0x180041093  jmp     loc_180041316
0x180041098  test    rdi, rdi
0x18004109b  jz      loc_1800412ED
0x1800410a1  cmp     [rdx], r14w
0x1800410a5  jz      loc_1800412ED
0x1800410ab  call    ?IsSystemOrAdmin@@YA_NXZ; IsSystemOrAdmin(void)
0x1800410b0  test    al, al
0x1800410b2  jnz     short loc_1800410DC
0x1800410b4  mov     rcx, [rsp+0D8h]; this
0x1800410bc  mov     ebx, 80070005h
0x1800410c1  mov     r9d, ebx; char *
0x1800410c4  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x1800410cb  mov     edx, 0F7h; void *
0x1800410d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800410d5  mov     eax, ebx
0x1800410d7  jmp     loc_180041316
0x1800410dc  mov     [rsp+0D8h+var_B8], r14; int
0x1800410e1  lea     rdx, [rsp+0D8h+var_B8]; void **
0x1800410e6  lea     rcx, _GUID_af2ba583_e24f_43f1_b92b_fc8125f93d16; riid
0x1800410ed  call    ?GetCoreWorker@@YAJAEBU_GUID@@PEAPEAX@Z; GetCoreWorker(_GUID const &,void * *)
0x1800410f2  mov     ebx, eax
0x1800410f4  test    eax, eax
0x1800410f6  jns     short loc_180041133
0x1800410f8  mov     rcx, [rsp+0D8h]; this
0x180041100  mov     r9d, eax; char *
0x180041103  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18004110a  mov     edx, 0FAh; void *
0x18004110f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041114  nop
0x180041115  mov     rcx, [rsp+0D8h+var_B8]
0x18004111a  test    rcx, rcx
0x18004111d  jz      short loc_18004112C
0x18004111f  mov     rax, [rcx]
0x180041122  mov     rax, [rax+10h]
0x180041126  call    _guard_dispatch_icall
0x18004112b  nop
0x18004112c  mov     eax, ebx
0x18004112e  jmp     loc_180041316
0x180041133  xorps   xmm0, xmm0
0x180041136  movups  xmmword ptr [rsp+0D8h+pguid.Data1], xmm0
0x18004113b  lea     rcx, [rsp+0D8h+pguid]; pguid
0x180041140  call    cs:__imp_CoCreateGuid
0x180041146  mov     ebx, eax
0x180041148  test    eax, eax
0x18004114a  jns     short loc_180041187
0x18004114c  mov     rcx, [rsp+0D8h]; this
0x180041154  mov     r9d, eax; char *
0x180041157  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18004115e  mov     edx, 0FEh; void *
0x180041163  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041168  nop
0x180041169  mov     rcx, [rsp+0D8h+var_B8]
0x18004116e  test    rcx, rcx
0x180041171  jz      short loc_180041180
0x180041173  mov     rax, [rcx]
0x180041176  mov     rax, [rax+10h]
0x18004117a  call    _guard_dispatch_icall
0x18004117f  nop
0x180041180  mov     eax, ebx
0x180041182  jmp     loc_180041316
0x180041187  mov     r8d, 28h ; '('; cchMax
0x18004118d  lea     rdx, [rsp+0D8h+sz]; lpsz
0x180041192  lea     rcx, [rsp+0D8h+pguid]; rguid
0x180041197  call    cs:__imp_StringFromGUID2
0x18004119d  test    eax, eax
0x18004119f  jnz     short loc_1800411E1
0x1800411a1  mov     rcx, [rsp+0D8h]; this
0x1800411a9  mov     ebx, 8007007Ah
0x1800411ae  mov     r9d, ebx; char *
0x1800411b1  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x1800411b8  mov     edx, 0FFh; void *
0x1800411bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800411c2  nop
0x1800411c3  mov     rcx, [rsp+0D8h+var_B8]
0x1800411c8  test    rcx, rcx
0x1800411cb  jz      short loc_1800411DA
0x1800411cd  mov     rdx, [rcx]
0x1800411d0  mov     rax, [rdx+10h]
0x1800411d4  call    _guard_dispatch_icall
0x1800411d9  nop
0x1800411da  mov     eax, ebx
0x1800411dc  jmp     loc_180041316
0x1800411e1  xorps   xmm0, xmm0
0x1800411e4  movups  [rsp+0D8h+Src], xmm0
0x1800411e9  xorps   xmm1, xmm1
0x1800411ec  movdqu  [rsp+0D8h+var_98], xmm1
0x1800411f2  mov     r8d, 0Fh
0x1800411f8  lea     rdx, aRestartrequest; "RestartRequest:"
0x1800411ff  lea     rcx, [rsp+0D8h+Src]
0x180041204  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180041209  nop
0x18004120a  lea     rax, [rsp+0D8h+sz]
0x18004120f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180041213  inc     r8
0x180041216  cmp     [rax+r8*2], r14w
0x18004121b  jnz     short loc_180041213
0x18004121d  lea     rdx, [rsp+0D8h+sz]
0x180041222  lea     rcx, [rsp+0D8h+Src]; Src
0x180041227  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18004122c  mov     rcx, [rsp+0D8h+var_B8]
0x180041231  mov     rax, [rcx]
0x180041234  lea     rdx, [rsp+0D8h+Src]
0x180041239  cmp     qword ptr [rsp+0D8h+var_98+8], 7
0x18004123f  cmova   rdx, qword ptr [rsp+0D8h+Src]
0x180041245  mov     r8, rdi
0x180041248  mov     rax, [rax+60h]
0x18004124c  call    _guard_dispatch_icall
0x180041251  mov     ebx, eax
0x180041253  test    eax, eax
0x180041255  jns     short loc_18004129A
0x180041257  mov     rcx, [rsp+0D8h]; this
0x18004125f  mov     r9d, eax; char *
0x180041262  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180041269  mov     edx, 103h; void *
0x18004126e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041273  nop
0x180041274  lea     rcx, [rsp+0D8h+Src]; void *
0x180041279  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004127e  nop
0x18004127f  mov     rcx, [rsp+0D8h+var_B8]
0x180041284  test    rcx, rcx
0x180041287  jz      short loc_180041296
0x180041289  mov     rax, [rcx]
0x18004128c  mov     rax, [rax+10h]
0x180041290  call    _guard_dispatch_icall
0x180041295  nop
0x180041296  mov     eax, ebx
0x180041298  jmp     short loc_180041316
0x18004129a  mov     [rsp+0D8h+var_B0], r14
0x18004129f  lea     rdx, [rsp+0D8h+Src]
0x1800412a4  cmp     qword ptr [rsp+0D8h+var_98+8], 7
0x1800412aa  cmova   rdx, qword ptr [rsp+0D8h+Src]
0x1800412b0  lea     rcx, [rsp+0D8h+var_B0]
0x1800412b5  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x1800412ba  mov     rax, [rsp+0D8h+var_B0]
0x1800412bf  mov     [rsp+0D8h+var_B0], r14
0x1800412c4  mov     [rsi], rax
0x1800412c7  lea     rcx, [rsp+0D8h+Src]; void *
0x1800412cc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800412d1  nop
0x1800412d2  mov     rcx, [rsp+0D8h+var_B8]
0x1800412d7  test    rcx, rcx
0x1800412da  jz      short loc_1800412E9
0x1800412dc  mov     rax, [rcx]
0x1800412df  mov     rax, [rax+10h]
0x1800412e3  call    _guard_dispatch_icall
0x1800412e8  nop
0x1800412e9  xor     eax, eax
0x1800412eb  jmp     short loc_180041316
0x1800412ed  mov     rcx, [rsp+0D8h]; this
0x1800412f5  mov     ebx, 80070057h
0x1800412fa  mov     r9d, ebx; char *
0x1800412fd  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180041304  mov     edx, 0F4h; void *
0x180041309  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004130e  mov     eax, ebx
0x180041310  jmp     short loc_180041316
0x180041312  mov     eax, dword ptr [rsp+0D8h+var_B8]
0x180041316  mov     rcx, [rsp+0D8h+var_28]
0x18004131e  xor     rcx, rsp; StackCookie
0x180041321  call    __security_check_cookie
0x180041326  mov     rbx, [rsp+0D8h+arg_0]
0x18004132e  add     rsp, 0C0h
0x180041335  pop     r14
0x180041337  pop     rdi
0x180041338  pop     rsi
0x180041339  retn
```
