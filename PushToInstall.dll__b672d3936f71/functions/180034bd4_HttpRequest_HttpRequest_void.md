# HttpRequest::~HttpRequest(void)

- ea: `0x180034bd4`
- end: `0x180034d0e`
- name: `??1HttpRequest@@QEAA@XZ`
- size: `314`
- prototype: `void __fastcall(HttpRequest *__hidden this)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180032ac0`
- `0x1800354bc`
- `0x18004d764`
- `0x18004db4e`
- `0x18004dc52`

## callees

- `0x18002fbb4`
- `0x180030aac`
- `0x180034b0c`
- `0x180034bd4`
- `0x1800354a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034cc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034cda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034cf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034cc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034cda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034cf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034bfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034bfe`

## pseudocode

```c
void __fastcall HttpRequest::~HttpRequest(HttpRequest *this)
{
  void *v2; // rcx
  bool v3; // zf
  signed int v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  signed int LastError; // eax
  int v8; // edx
  unsigned int v9; // r8d
  signed int v10; // eax
  int v11; // edx
  unsigned int v12; // r8d

  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((char *)this + 248);
  v2 = (void *)*((_QWORD *)this + 27);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = *((_QWORD *)this + 26) == 0;
  *((_QWORD *)this + 25) = &Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable';
  if ( !v3 )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::InternalClose((char *)this + 200) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v8, v9);
      __debugbreak();
    }
    *((_QWORD *)this + 26) = 0;
  }
  v3 = *((_QWORD *)this + 24) == 0;
  *((_QWORD *)this + 23) = &Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable';
  if ( !v3 )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::InternalClose((char *)this + 184) )
    {
      v10 = GetLastError();
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
      JUMPOUT(0x180034D0DLL);
    }
    *((_QWORD *)this + 24) = 0;
  }
  v3 = *((_QWORD *)this + 22) == 0;
  *((_QWORD *)this + 21) = &Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable';
  if ( !v3 )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::InternalClose((char *)this + 168) )
    {
      v4 = GetLastError();
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
      __debugbreak();
    }
    *((_QWORD *)this + 22) = 0;
  }
  std::wstring::_Tidy_deallocate((char *)this + 128);
  std::wstring::_Tidy_deallocate((char *)this + 96);
  std::wstring::_Tidy_deallocate((char *)this + 64);
  std::wstring::_Tidy_deallocate((char *)this + 32);
  std::wstring::_Tidy_deallocate(this);
}

```

## disassembly

```asm
0x180034bd4  mov     [rsp+arg_0], rbx
0x180034bd9  mov     [rsp+arg_8], rbp
0x180034bde  push    rdi
0x180034bdf  sub     rsp, 20h
0x180034be3  mov     rbx, rcx
0x180034be6  add     rcx, 0F8h
0x180034bed  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180034bf2  mov     rcx, [rbx+0D8h]; pv
0x180034bf9  test    rcx, rcx
0x180034bfc  jz      short loc_180034C04
0x180034bfe  call    cs:__imp_CoTaskMemFree
0x180034c04  lea     rdi, [rbx+0C8h]
0x180034c0b  cmp     qword ptr [rdi+8], 0
0x180034c10  lea     rbp, ??_7?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable'
0x180034c17  mov     [rdi], rbp
0x180034c1a  jz      short loc_180034C34
0x180034c1c  mov     rcx, rdi
0x180034c1f  call    ?InternalClose@?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::InternalClose(void)
0x180034c24  test    al, al
0x180034c26  jz      loc_180034CDA
0x180034c2c  mov     qword ptr [rdi+8], 0
0x180034c34  lea     rdi, [rbx+0B8h]
0x180034c3b  cmp     qword ptr [rdi+8], 0
0x180034c40  mov     [rdi], rbp
0x180034c43  jz      short loc_180034C5D
0x180034c45  mov     rcx, rdi
0x180034c48  call    ?InternalClose@?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::InternalClose(void)
0x180034c4d  test    al, al
0x180034c4f  jz      loc_180034CF4
0x180034c55  mov     qword ptr [rdi+8], 0
0x180034c5d  lea     rdi, [rbx+0A8h]
0x180034c64  cmp     qword ptr [rdi+8], 0
0x180034c69  mov     [rdi], rbp
0x180034c6c  jz      short loc_180034C82
0x180034c6e  mov     rcx, rdi
0x180034c71  call    ?InternalClose@?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::InternalClose(void)
0x180034c76  test    al, al
0x180034c78  jz      short loc_180034CC0
0x180034c7a  mov     qword ptr [rdi+8], 0
0x180034c82  lea     rcx, [rbx+80h]
0x180034c89  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034c8e  lea     rcx, [rbx+60h]
0x180034c92  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034c97  lea     rcx, [rbx+40h]
0x180034c9b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034ca0  lea     rcx, [rbx+20h]
0x180034ca4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034ca9  mov     rcx, rbx
0x180034cac  mov     rbx, [rsp+28h+arg_0]
0x180034cb1  mov     rbp, [rsp+28h+arg_8]
0x180034cb6  add     rsp, 20h
0x180034cba  pop     rdi
0x180034cbb  jmp     ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034cc0  call    cs:__imp_GetLastError
0x180034cc6  test    eax, eax
0x180034cc8  jle     short loc_180034CD2
0x180034cca  movzx   eax, ax
0x180034ccd  or      eax, 80070000h
0x180034cd2  mov     ecx, eax; this
0x180034cd4  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180034cd9  int     3; Trap to Debugger
0x180034cda  call    cs:__imp_GetLastError
0x180034ce0  test    eax, eax
0x180034ce2  jle     short loc_180034CEC
0x180034ce4  movzx   eax, ax
0x180034ce7  or      eax, 80070000h
0x180034cec  mov     ecx, eax; this
0x180034cee  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180034cf3  int     3; Trap to Debugger
0x180034cf4  call    cs:__imp_GetLastError
0x180034cfa  test    eax, eax
0x180034cfc  jle     short loc_180034D06
0x180034cfe  movzx   eax, ax
0x180034d01  or      eax, 80070000h
0x180034d06  mov     ecx, eax; this
0x180034d08  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
