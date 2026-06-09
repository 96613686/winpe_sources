# Uev::TemplateFolder::GetTemplateFolder(void)

- ea: `0x14003c7e8`
- end: `0x14003c8dc`
- name: `?GetTemplateFolder@TemplateFolder@Uev@@QEAAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `244`
- prototype: `void **()`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14003c630`
- `0x14003e0c0`
- `0x140063f54`

## callees

- `0x140003e50`
- `0x140004a6c`
- `0x14000c1cc`
- `0x14000c3a4`
- `0x14003c7e8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14003c8b2`
- `ole32!CoTaskMemFree` at `0x14003c8b2`
- `SHELL32!SHGetKnownFolderPath` at `0x14003c82d`
- `SHELL32!SHGetKnownFolderPath` at `0x14003c82d`

## string_xrefs

- `0x14003c89a`: `\Microsoft\UEV\Templates`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void **Uev::TemplateFolder::GetTemplateFolder()
{
  __int64 v0; // r8
  unsigned __int64 v1; // rdx
  __int64 v2; // rbx
  void **v3; // rdi
  void *Src; // [rsp+20h] [rbp-18h] BYREF

  if ( !qword_1400CB330 )
  {
    Src = 0;
    if ( SHGetKnownFolderPath(&FOLDERID_ProgramData, 0x8000u, 0, (PWSTR *)&Src) >= 0 )
    {
      v1 = -1;
      do
        ++v1;
      while ( *((_WORD *)Src + v1) );
      if ( v1 > qword_1400CB338 )
      {
        std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
          &qword_1400CB320,
          v1,
          v0,
          Src);
      }
      else
      {
        v2 = 2 * v1;
        qword_1400CB330 = v1;
        v3 = &qword_1400CB320;
        if ( (unsigned __int64)qword_1400CB338 > 7 )
          v3 = (void **)qword_1400CB320;
        memmove_0(v3, Src, 2 * v1);
        *(_WORD *)((char *)v3 + v2) = 0;
      }
      std::wstring::_Append<wchar_t>(&qword_1400CB320);
    }
    CoTaskMemFree(Src);
  }
  return &qword_1400CB320;
}

```

## disassembly

```asm
0x14003c7e8  mov     r11, rsp
0x14003c7eb  mov     [r11+8], rbx
0x14003c7ef  mov     [r11+10h], rsi
0x14003c7f3  push    rdi
0x14003c7f4  sub     rsp, 30h
0x14003c7f8  mov     rax, cs:__security_cookie
0x14003c7ff  xor     rax, rsp
0x14003c802  mov     [rsp+38h+var_10], rax
0x14003c807  xor     esi, esi
0x14003c809  cmp     cs:qword_1400CB330, rsi
0x14003c810  jnz     loc_14003C8B8
0x14003c816  lea     r9, [r11-18h]; ppszPath
0x14003c81a  mov     [r11-18h], rsi
0x14003c81e  xor     r8d, r8d; hToken
0x14003c821  lea     rcx, FOLDERID_ProgramData; rfid
0x14003c828  mov     edx, 8000h; dwFlags
0x14003c82d  call    cs:__imp_SHGetKnownFolderPath
0x14003c833  test    eax, eax
0x14003c835  js      short loc_14003C8AD
0x14003c837  mov     r9, [rsp+38h+Src]
0x14003c83c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14003c840  inc     rdx
0x14003c843  cmp     [r9+rdx*2], si
0x14003c848  jnz     short loc_14003C840
0x14003c84a  mov     rax, cs:qword_1400CB338
0x14003c851  cmp     rdx, rax
0x14003c854  ja      short loc_14003C888
0x14003c856  lea     rbx, [rdx+rdx]
0x14003c85a  mov     cs:qword_1400CB330, rdx
0x14003c861  cmp     rax, 7
0x14003c865  lea     rdi, qword_1400CB320
0x14003c86c  mov     r8, rbx; Size
0x14003c86f  mov     rdx, r9; Src
0x14003c872  cmova   rdi, cs:qword_1400CB320
0x14003c87a  mov     rcx, rdi; void *
0x14003c87d  call    memmove_0
0x14003c882  mov     [rbx+rdi], si
0x14003c886  jmp     short loc_14003C894
0x14003c888  lea     rcx, qword_1400CB320
0x14003c88f  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x14003c894  mov     r8d, 18h
0x14003c89a  lea     rdx, aMicrosoftUevTe; "\\Microsoft\\UEV\\Templates"
0x14003c8a1  lea     rcx, qword_1400CB320; Src
0x14003c8a8  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14003c8ad  mov     rcx, [rsp+38h+Src]; pv
0x14003c8b2  call    cs:__imp_CoTaskMemFree
0x14003c8b8  lea     rax, qword_1400CB320
0x14003c8bf  mov     rcx, [rsp+38h+var_10]
0x14003c8c4  xor     rcx, rsp; StackCookie
0x14003c8c7  call    __security_check_cookie
0x14003c8cc  mov     rbx, [rsp+38h+arg_0]
0x14003c8d1  mov     rsi, [rsp+38h+arg_8]
0x14003c8d6  add     rsp, 30h
0x14003c8da  pop     rdi
0x14003c8db  retn
```
