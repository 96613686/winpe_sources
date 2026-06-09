# std::list<std::pair<DiagHubCommon::LogLevel const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<DiagHubCommon::LogLevel const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>::~list<std::pair<DiagHubCommon::LogLevel const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<DiagHubCommon::LogLevel const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>(void)

- ea: `0x14000b7b4`
- end: `0x14000b819`
- name: `??1?$list@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$allocator@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000b2ac`
- `0x14001564f`
- `0x140015bf0`

## callees

- `0x140003010`
- `0x14000b7b4`
- `0x14001382c`

## pseudocode

```c
void __fastcall std::list<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>::~list<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>(
        void **a1)
{
  _QWORD **v1; // rdx
  _QWORD *v3; // rdi
  _QWORD *v4; // rbx

  v1 = (_QWORD **)*a1;
  **((_QWORD **)*a1 + 1) = 0;
  v3 = *v1;
  if ( *v1 )
  {
    do
    {
      v4 = (_QWORD *)*v3;
      std::wstring::~wstring(v3 + 3);
      operator delete(v3);
      v3 = v4;
    }
    while ( v4 );
  }
  operator delete(*a1);
}

```

## disassembly

```asm
0x14000b7b4  mov     [rsp+arg_8], rbx
0x14000b7b9  mov     [rsp+arg_10], rsi
0x14000b7be  push    rdi
0x14000b7bf  sub     rsp, 20h
0x14000b7c3  mov     rdx, [rcx]
0x14000b7c6  mov     rsi, rcx
0x14000b7c9  mov     rax, [rdx+8]
0x14000b7cd  mov     qword ptr [rax], 0
0x14000b7d4  mov     rdi, [rdx]
0x14000b7d7  test    rdi, rdi
0x14000b7da  jz      short loc_14000B7FD
0x14000b7dc  mov     rbx, [rdi]
0x14000b7df  lea     rcx, [rdi+18h]
0x14000b7e3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000b7e8  mov     edx, 38h ; '8'
0x14000b7ed  mov     rcx, rdi; Block
0x14000b7f0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000b7f5  mov     rdi, rbx
0x14000b7f8  test    rbx, rbx
0x14000b7fb  jnz     short loc_14000B7DC
0x14000b7fd  mov     rcx, [rsi]; Block
0x14000b800  mov     edx, 38h ; '8'
0x14000b805  mov     rbx, [rsp+28h+arg_8]
0x14000b80a  mov     rsi, [rsp+28h+arg_10]
0x14000b80f  add     rsp, 20h
0x14000b813  pop     rdi
0x14000b814  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
