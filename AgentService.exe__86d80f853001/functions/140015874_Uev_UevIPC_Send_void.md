# Uev::UevIPC::Send(void)

- ea: `0x140015874`
- end: `0x140015a1a`
- name: `?Send@UevIPC@Uev@@QEAAXXZ`
- size: `422`
- prototype: `void __fastcall(Uev::UevIPC *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140015224`
- `0x140089ef0`

## callees

- `0x140003e50`
- `0x140003e74`
- `0x140004a6c`
- `0x140004b14`
- `0x14000adb4`
- `0x14000ba60`
- `0x14000c3a4`
- `0x14000d7b4`
- `0x140013228`
- `0x140013f24`
- `0x140015874`
- `0x140015a68`
- `0x14009b010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x140015903`
- `KERNEL32!GetCurrentProcessId` at `0x140015903`
- `KERNEL32!ProcessIdToSessionId` at `0x14001590f`
- `KERNEL32!ProcessIdToSessionId` at `0x14001590f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Uev::UevIPC::Send(Uev::UevIPC *this)
{
  _QWORD *v2; // rax
  DWORD CurrentProcessId; // eax
  __int64 v4; // rax
  __int64 v5; // r8
  unsigned __int64 v6; // rdx
  char *v7; // rdi
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdi
  void (__fastcall *v12)(__int64, __int64); // rbx
  __int64 v13; // rax
  _BYTE v14[32]; // [rsp+28h] [rbp-61h] BYREF
  DWORD pSessionId; // [rsp+48h] [rbp-41h] BYREF
  __int128 v16; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v17[32]; // [rsp+60h] [rbp-29h] BYREF
  wchar_t Buffer[4]; // [rsp+80h] [rbp-9h] BYREF
  __int128 v19; // [rsp+88h] [rbp-1h]
  __int128 v20; // [rsp+98h] [rbp+Fh]
  __int128 v21; // [rsp+A8h] [rbp+1Fh]
  __int64 v22; // [rsp+B8h] [rbp+2Fh]

  v16 = 0;
  v2 = operator new(0x60u);
  *v2 = v2;
  v2[1] = v2;
  v2[2] = v2;
  *((_WORD *)v2 + 12) = 257;
  *(_QWORD *)&v16 = v2;
  (*(void (__fastcall **)(Uev::UevIPC *, __int128 *))(*(_QWORD *)this + 8LL))(this, &v16);
  pSessionId = 0;
  wcscpy(Buffer, L"777");
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  CurrentProcessId = GetCurrentProcessId();
  if ( ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    swprintf_s(Buffer, 0x20u, L"%d", pSessionId);
  v4 = std::map<std::wstring,std::wstring>::operator[](&v16, Uev::SessionID);
  v6 = -1;
  do
    ++v6;
  while ( Buffer[v6] );
  if ( v6 > *(_QWORD *)(v4 + 24) )
  {
    std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
      (char **)v4,
      v6,
      v5,
      Buffer);
  }
  else
  {
    if ( *(_QWORD *)(v4 + 24) <= 7u )
      v7 = (char *)v4;
    else
      v7 = *(char **)v4;
    *(_QWORD *)(v4 + 16) = v6;
    v8 = 2 * v6;
    memmove_0(v7, Buffer, 2 * v6);
    *(_WORD *)&v7[v8] = 0;
  }
  v9 = std::map<std::wstring,std::wstring>::operator[](&v16, Uev::EventName);
  std::wstring::operator=(v9, (char *)this + 8);
  Uev::UevIPC::SerializeMapToJson(v10, v17, &v16);
  v11 = *((_QWORD *)this + 5);
  v12 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 8LL);
  v13 = std::wstring::wstring((__int64)v14, (__int64)v17);
  v12(v11, v13);
  std::wstring::_Tidy_deallocate(v17);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v16);
}

```

## disassembly

```asm
0x140015874  mov     [rsp-8+arg_8], rbx
0x140015879  mov     [rsp-8+arg_10], rsi
0x14001587e  push    rbp
0x14001587f  push    rdi
0x140015880  push    r14
0x140015882  lea     rbp, [rsp-47h]
0x140015887  sub     rsp, 0D0h
0x14001588e  mov     rax, cs:__security_cookie
0x140015895  xor     rax, rsp
0x140015898  mov     [rbp+57h+var_20], rax
0x14001589c  mov     rsi, rcx
0x14001589f  xorps   xmm0, xmm0
0x1400158a2  movdqu  [rbp+57h+var_90], xmm0
0x1400158a7  mov     ecx, 60h ; '`'; Size
0x1400158ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400158b1  mov     [rax], rax
0x1400158b4  mov     [rax+8], rax
0x1400158b8  mov     [rax+10h], rax
0x1400158bc  mov     word ptr [rax+18h], 101h
0x1400158c2  mov     qword ptr [rbp+57h+var_90], rax
0x1400158c6  mov     rax, [rsi]
0x1400158c9  lea     rdx, [rbp+57h+var_90]
0x1400158cd  mov     rcx, rsi
0x1400158d0  mov     rax, [rax+8]
0x1400158d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400158d9  xor     r14d, r14d
0x1400158dc  mov     [rbp+57h+pSessionId], r14d
0x1400158e0  mov     rax, 3700370037h
0x1400158ea  mov     qword ptr [rbp+57h+Buffer], rax
0x1400158ee  xorps   xmm0, xmm0
0x1400158f1  xor     eax, eax
0x1400158f3  movups  [rbp+57h+var_58], xmm0
0x1400158f7  movups  [rbp+57h+var_48], xmm0
0x1400158fb  movups  [rbp+57h+var_38], xmm0
0x1400158ff  mov     [rbp+57h+var_28], rax
0x140015903  call    cs:__imp_GetCurrentProcessId
0x140015909  mov     ecx, eax; dwProcessId
0x14001590b  lea     rdx, [rbp+57h+pSessionId]; pSessionId
0x14001590f  call    cs:__imp_ProcessIdToSessionId
0x140015915  test    eax, eax
0x140015917  jz      short loc_140015931
0x140015919  mov     r9d, [rbp+57h+pSessionId]
0x14001591d  lea     r8, aD; "%d"
0x140015924  lea     edx, [r14+20h]; BufferCount
0x140015928  lea     rcx, [rbp+57h+Buffer]; Buffer
0x14001592c  call    swprintf_s
0x140015931  lea     rdx, ?SessionID@Uev@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Uev::SessionID
0x140015938  lea     rcx, [rbp+57h+var_90]
0x14001593c  call    ??A?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEBV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring const &)
0x140015941  lea     rcx, [rbp+57h+Buffer]
0x140015945  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140015949  inc     rdx
0x14001594c  cmp     [rcx+rdx*2], r14w
0x140015951  jnz     short loc_140015949
0x140015953  cmp     rdx, [rax+18h]
0x140015957  ja      short loc_140015986
0x140015959  cmp     qword ptr [rax+18h], 7
0x14001595e  jbe     short loc_140015965
0x140015960  mov     rdi, [rax]
0x140015963  jmp     short loc_140015968
0x140015965  mov     rdi, rax
0x140015968  mov     [rax+10h], rdx
0x14001596c  lea     rbx, [rdx+rdx]
0x140015970  mov     r8, rbx; Size
0x140015973  lea     rdx, [rbp+57h+Buffer]; Src
0x140015977  mov     rcx, rdi; void *
0x14001597a  call    memmove_0
0x14001597f  mov     [rbx+rdi], r14w
0x140015984  jmp     short loc_140015992
0x140015986  lea     r9, [rbp+57h+Buffer]
0x14001598a  mov     rcx, rax
0x14001598d  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x140015992  lea     rdx, ?EventName@Uev@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Uev::EventName
0x140015999  lea     rcx, [rbp+57h+var_90]
0x14001599d  call    ??A?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEBV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring const &)
0x1400159a2  mov     rcx, rax
0x1400159a5  lea     rdx, [rsi+8]
0x1400159a9  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1400159ae  lea     r8, [rbp+57h+var_90]
0x1400159b2  lea     rdx, [rbp+57h+var_80]
0x1400159b6  call    ?SerializeMapToJson@UevIPC@Uev@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@4@@Z; Uev::UevIPC::SerializeMapToJson(std::map<std::wstring,std::wstring> const &)
0x1400159bb  nop
0x1400159bc  mov     rdi, [rsi+28h]
0x1400159c0  mov     rax, [rdi]
0x1400159c3  mov     rbx, [rax+8]
0x1400159c7  lea     rdx, [rbp+57h+var_80]
0x1400159cb  lea     rcx, [rbp+57h+var_B8]
0x1400159cf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400159d4  mov     rdx, rax
0x1400159d7  mov     rcx, rdi
0x1400159da  mov     rax, rbx
0x1400159dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400159e2  nop
0x1400159e3  lea     rcx, [rbp+57h+var_80]
0x1400159e7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400159ec  nop
0x1400159ed  lea     rcx, [rbp+57h+var_90]
0x1400159f1  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1400159f6  mov     rcx, [rbp+57h+var_20]
0x1400159fa  xor     rcx, rsp; StackCookie
0x1400159fd  call    __security_check_cookie
0x140015a02  lea     r11, [rsp+0E0h+var_10]
0x140015a0a  mov     rbx, [r11+28h]
0x140015a0e  mov     rsi, [r11+30h]
0x140015a12  mov     rsp, r11
0x140015a15  pop     r14
0x140015a17  pop     rdi
0x140015a18  pop     rbp
0x140015a19  retn
```
