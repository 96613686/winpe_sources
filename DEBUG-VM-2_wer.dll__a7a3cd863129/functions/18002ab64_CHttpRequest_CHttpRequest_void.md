# CHttpRequest::~CHttpRequest(void)

- ea: `0x18002ab64`
- end: `0x18002ac7d`
- name: `??1CHttpRequest@@QEAA@XZ`
- size: `281`
- prototype: `void __fastcall(CHttpRequest *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002eae8`
- `0x180092380`

## callees

- `0x180007e10`
- `0x18000dad0`
- `0x18002ab64`
- `0x180039eb4`
- `0x18003bf14`
- `0x180043d04`
- `0x18004bc0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ac25`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ac2f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ac39`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ac25`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ac2f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ac39`

## pseudocode

```c
void __fastcall CHttpRequest::~CHttpRequest(CHttpRequest *this, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  char *v5; // rax

  if ( *((_QWORD *)this + 4) != -1 && *((_QWORD *)this + 4) != 0 )
    CHttpRequest::AbortRequest(this);
  if ( *(_QWORD *)this )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
  if ( *((_QWORD *)this + 2) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
  if ( *((_QWORD *)this + 1) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
  v4 = 520;
  v5 = (char *)this + 304;
  do
  {
    *v5++ = 0;
    --v4;
  }
  while ( v4 );
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 1000);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 968);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 936);
  utl::unique_ptr<IXmlWriter,tlx::release_delete>::~unique_ptr<IXmlWriter,tlx::release_delete>((char *)this + 912);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 880);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 832);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 272);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 192);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((char *)this + 48);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((char *)this + 32);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((char *)this + 24);
  tlx::unique_any<tlx::handle_traits<void *,int (*)(void *),&int WinHttpCloseHandle(void *),0>>::~unique_any<tlx::handle_traits<void *,int (*)(void *),&int WinHttpCloseHandle(void *),0>>((char *)this + 16);
  tlx::unique_any<tlx::handle_traits<void *,int (*)(void *),&int WinHttpCloseHandle(void *),0>>::~unique_any<tlx::handle_traits<void *,int (*)(void *),&int WinHttpCloseHandle(void *),0>>((char *)this + 8);
  tlx::unique_any<tlx::handle_traits<void *,int (*)(void *),&int WinHttpCloseHandle(void *),0>>::~unique_any<tlx::handle_traits<void *,int (*)(void *),&int WinHttpCloseHandle(void *),0>>(this);
}

```

## disassembly

```asm
0x18002ab64  push    rbx
0x18002ab66  push    rsi
0x18002ab67  push    rdi
0x18002ab68  push    r14
0x18002ab6a  sub     rsp, 28h
0x18002ab6e  mov     rbx, rcx
0x18002ab71  mov     rax, [rcx+20h]
0x18002ab75  inc     rax
0x18002ab78  cmp     rax, 1
0x18002ab7c  jbe     short loc_18002AB83
0x18002ab7e  call    ?AbortRequest@CHttpRequest@@QEAAXXZ; CHttpRequest::AbortRequest(void)
0x18002ab83  cmp     qword ptr [rbx], 0
0x18002ab87  jz      short loc_18002AB8E
0x18002ab89  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002ab8e  cmp     qword ptr [rbx+10h], 0
0x18002ab93  jz      short loc_18002AB9A
0x18002ab95  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002ab9a  cmp     qword ptr [rbx+8], 0
0x18002ab9f  jz      short loc_18002ABA6
0x18002aba1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002aba6  mov     ecx, 208h
0x18002abab  lea     rax, [rbx+130h]
0x18002abb2  mov     byte ptr [rax], 0
0x18002abb5  inc     rax
0x18002abb8  sub     rcx, 1
0x18002abbc  jnz     short loc_18002ABB2
0x18002abbe  lea     rcx, [rbx+3E8h]; void *
0x18002abc5  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18002abca  lea     rcx, [rbx+3C8h]; void *
0x18002abd1  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18002abd6  lea     rcx, [rbx+3A8h]; void *
0x18002abdd  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18002abe2  lea     rcx, [rbx+390h]
0x18002abe9  call    ??1?$unique_ptr@UIXmlWriter@@Urelease_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<IXmlWriter,tlx::release_delete>::~unique_ptr<IXmlWriter,tlx::release_delete>(void)
0x18002abee  lea     rcx, [rbx+370h]; void *
0x18002abf5  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18002abfa  lea     rcx, [rbx+340h]; void *
0x18002ac01  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18002ac06  lea     rcx, [rbx+110h]; void *
0x18002ac0d  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18002ac12  lea     rcx, [rbx+0C0h]; void *
0x18002ac19  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18002ac1e  lea     rcx, [rbx+98h]; lpCriticalSection
0x18002ac25  call    cs:__imp_DeleteCriticalSection
0x18002ac2b  lea     rcx, [rbx+70h]; lpCriticalSection
0x18002ac2f  call    cs:__imp_DeleteCriticalSection
0x18002ac35  lea     rcx, [rbx+48h]; lpCriticalSection
0x18002ac39  call    cs:__imp_DeleteCriticalSection
0x18002ac3f  lea     rcx, [rbx+30h]
0x18002ac43  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18002ac48  lea     rcx, [rbx+20h]
0x18002ac4c  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18002ac51  lea     rcx, [rbx+18h]
0x18002ac55  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18002ac5a  lea     rcx, [rbx+10h]
0x18002ac5e  call    ??1?$unique_any@U?$handle_traits@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,int (*)(void *),&WinHttpCloseHandle(void *),0>>::~unique_any<tlx::handle_traits<void *,int (*)(void *),&WinHttpCloseHandle(void *),0>>(void)
0x18002ac63  lea     rcx, [rbx+8]
0x18002ac67  call    ??1?$unique_any@U?$handle_traits@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,int (*)(void *),&WinHttpCloseHandle(void *),0>>::~unique_any<tlx::handle_traits<void *,int (*)(void *),&WinHttpCloseHandle(void *),0>>(void)
0x18002ac6c  mov     rcx, rbx
0x18002ac6f  add     rsp, 28h
0x18002ac73  pop     r14
0x18002ac75  pop     rdi
0x18002ac76  pop     rsi
0x18002ac77  pop     rbx
0x18002ac78  jmp     ??1?$unique_any@U?$handle_traits@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,int (*)(void *),&WinHttpCloseHandle(void *),0>>::~unique_any<tlx::handle_traits<void *,int (*)(void *),&WinHttpCloseHandle(void *),0>>(void)
```
