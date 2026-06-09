# ConfigPathNode::SetAssociatedVDirPhysicalPath(IAppHostElement *)

- ea: `0x18000d6bc`
- end: `0x18000d88c`
- name: `?SetAssociatedVDirPhysicalPath@ConfigPathNode@@IEAAXPEAUIAppHostElement@@@Z`
- size: `464`
- prototype: `void __fastcall(ConfigPathNode *__hidden this, struct IAppHostElement *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d9ac`

## callees

- `0x1800018a0`
- `0x180001910`
- `0x180001a30`
- `0x1800021a4`
- `0x1800021e0`
- `0x1800039ec`
- `0x18000c6a0`
- `0x18000d6bc`
- `0x1800105a0`
- `0x1800126b0`
- `0x180012ea8`
- `0x180012f3c`
- `0x1800130a0`
- `0x180014010`

## string_xrefs

- `0x18000d73d`: `physicalPath`

## pseudocode

```c
void __fastcall ConfigPathNode::SetAssociatedVDirPhysicalPath(ConfigPathNode *this, struct IAppHostElement *a2)
{
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int pExceptionObject; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR lpSrc; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v10; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v11[4]; // [rsp+38h] [rbp-C8h] BYREF
  int v12; // [rsp+3Ch] [rbp-C4h]
  unsigned __int16 *v13; // [rsp+40h] [rbp-C0h]
  int v14; // [rsp+48h] [rbp-B8h]
  __int16 v15; // [rsp+50h] [rbp-B0h] BYREF

  if ( dword_18001E588 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18001E588);
    if ( dword_18001E588 == -1 )
    {
      atexit(ConfigPathNode::SetAssociatedVDirPhysicalPath_::_2_::_dynamic_atexit_destructor_for__bstrPhysicalPathString__);
      Init_thread_footer(&dword_18001E588);
    }
  }
  Helpers::EnsureInitializedSerialized((struct ScopedBSTR *)&qword_18001E598, (OLECHAR *)L"physicalPath");
  v10 = 0;
  v4 = ((__int64 (__fastcall *)(struct IAppHostElement *, _QWORD, __int64 *))a2->lpVtbl->GetPropertyByName)(
         a2,
         qword_18001E598,
         &v10);
  if ( v4 < 0 )
  {
    pExceptionObject = v4;
    throw (long *)&pExceptionObject;
  }
  lpSrc = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v10 + 56LL))(v10, &lpSrc);
  if ( v5 < 0 )
  {
    pExceptionObject = v5;
    throw (long *)&pExceptionObject;
  }
  v11[2] = 0;
  v12 = 520;
  v13 = (unsigned __int16 *)&v15;
  v14 = 0;
  v15 = 0;
  v6 = STRU::CopyAndExpandEnvironmentStrings((STRU *)v11, lpSrc);
  if ( v6 < 0 )
  {
    pExceptionObject = v6;
    throw (long *)&pExceptionObject;
  }
  v7 = String::Initialize((ConfigPathNode *)((char *)this + 40), v13);
  if ( v7 < 0 )
  {
    pExceptionObject = v7;
    throw (long *)&pExceptionObject;
  }
  InvasivePtr<AppHostConfigPathNavigator>::Reset((char *)this + 32);
  BUFFER::~BUFFER((BUFFER *)v11);
  ScopedBSTR::Reset((ScopedBSTR *)&lpSrc);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
}

```

## disassembly

```asm
0x18000d6bc  mov     [rsp-8+arg_10], rbx
0x18000d6c1  mov     [rsp-8+arg_18], rdi
0x18000d6c6  push    rbp
0x18000d6c7  lea     rbp, [rsp-170h]
0x18000d6cf  sub     rsp, 270h
0x18000d6d6  mov     rax, cs:__security_cookie
0x18000d6dd  xor     rax, rsp
0x18000d6e0  mov     [rbp+170h+var_10], rax
0x18000d6e7  mov     rdi, rdx
0x18000d6ea  mov     rbx, rcx
0x18000d6ed  mov     edx, cs:_tls_index
0x18000d6f3  mov     rax, gs:58h
0x18000d6fc  mov     ecx, 4
0x18000d701  mov     rax, [rax+rdx*8]
0x18000d705  mov     edx, [rcx+rax]
0x18000d708  cmp     cs:dword_18001E588, edx
0x18000d70e  jle     short loc_18000D73D
0x18000d710  lea     rcx, dword_18001E588
0x18000d717  call    _Init_thread_header
0x18000d71c  cmp     cs:dword_18001E588, 0FFFFFFFFh
0x18000d723  jnz     short loc_18000D73D
0x18000d725  lea     rcx, _ConfigPathNode__SetAssociatedVDirPhysicalPath____2____dynamic_atexit_destructor_for__bstrPhysicalPathString__; void (__cdecl *)()
0x18000d72c  call    atexit
0x18000d731  lea     rcx, dword_18001E588
0x18000d738  call    _Init_thread_footer
0x18000d73d  lea     rdx, aPhysicalpath; "physicalPath"
0x18000d744  lea     rcx, qword_18001E598; this
0x18000d74b  call    ?EnsureInitializedSerialized@Helpers@@SAXAEAVScopedBSTR@@PEBG@Z; Helpers::EnsureInitializedSerialized(ScopedBSTR &,ushort const *)
0x18000d750  mov     [rsp+270h+var_240], 0
0x18000d759  mov     rax, [rdi]
0x18000d75c  lea     r8, [rsp+270h+var_240]
0x18000d761  mov     rdx, cs:qword_18001E598
0x18000d768  mov     rcx, rdi
0x18000d76b  mov     rax, [rax+58h]
0x18000d76f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d774  test    eax, eax
0x18000d776  jns     short loc_18000D78E
0x18000d778  mov     [rsp+270h+pExceptionObject], eax
0x18000d77c  lea     rdx, _TI1J; pThrowInfo
0x18000d783  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x18000d788  call    _CxxThrowException_0
0x18000d78e  mov     [rsp+270h+lpSrc], 0
0x18000d797  mov     rcx, [rsp+270h+var_240]
0x18000d79c  mov     rax, [rcx]
0x18000d79f  lea     rdx, [rsp+270h+lpSrc]
0x18000d7a4  mov     rax, [rax+38h]
0x18000d7a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7ad  test    eax, eax
0x18000d7af  jns     short loc_18000D7C7
0x18000d7b1  mov     [rsp+270h+pExceptionObject], eax
0x18000d7b5  lea     rdx, _TI1J; pThrowInfo
0x18000d7bc  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x18000d7c1  call    _CxxThrowException_0
0x18000d7c7  mov     [rsp+270h+var_236], 0
0x18000d7cc  mov     [rsp+270h+var_234], 208h
0x18000d7d4  lea     rax, [rsp+270h+var_220]
0x18000d7d9  mov     [rsp+270h+var_230], rax
0x18000d7de  mov     [rsp+270h+var_228], 0
0x18000d7e6  xor     eax, eax
0x18000d7e8  mov     [rsp+270h+var_220], ax
0x18000d7ed  mov     rdx, [rsp+270h+lpSrc]; lpSrc
0x18000d7f2  lea     rcx, [rsp+270h+var_238]; this
0x18000d7f7  call    ?CopyAndExpandEnvironmentStrings@STRU@@QEAAJPEBG@Z; STRU::CopyAndExpandEnvironmentStrings(ushort const *)
0x18000d7fc  test    eax, eax
0x18000d7fe  jns     short loc_18000D816
0x18000d800  mov     [rsp+270h+pExceptionObject], eax
0x18000d804  lea     rdx, _TI1J; pThrowInfo
0x18000d80b  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x18000d810  call    _CxxThrowException_0
0x18000d816  lea     rcx, [rbx+28h]; this
0x18000d81a  mov     rdx, [rsp+270h+var_230]; unsigned __int16 *
0x18000d81f  call    ?Initialize@String@@QEAAJPEBG@Z; String::Initialize(ushort const *)
0x18000d824  test    eax, eax
0x18000d826  jns     short loc_18000D83E
0x18000d828  mov     [rsp+270h+pExceptionObject], eax
0x18000d82c  lea     rdx, _TI1J; pThrowInfo
0x18000d833  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x18000d838  call    _CxxThrowException_0
0x18000d83e  lea     rcx, [rbx+20h]
0x18000d842  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x18000d847  nop
0x18000d848  lea     rcx, [rsp+270h+var_238]; this
0x18000d84d  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000d852  nop
0x18000d853  lea     rcx, [rsp+270h+lpSrc]; this
0x18000d858  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000d85d  nop
0x18000d85e  lea     rcx, [rsp+270h+var_240]
0x18000d863  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d868  mov     rcx, [rbp+170h+var_10]
0x18000d86f  xor     rcx, rsp; StackCookie
0x18000d872  call    __security_check_cookie
0x18000d877  lea     r11, [rsp+270h+var_s0]
0x18000d87f  mov     rbx, [r11+20h]
0x18000d883  mov     rdi, [r11+28h]
0x18000d887  mov     rsp, r11
0x18000d88a  pop     rbp
0x18000d88b  retn
```
