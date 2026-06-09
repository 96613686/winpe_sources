# std::unique_ptr<RemoteFileBrowseClient,std::default_delete<RemoteFileBrowseClient>>::~unique_ptr<RemoteFileBrowseClient,std::default_delete<RemoteFileBrowseClient>>(void)

- ea: `0x18000b2f4`
- end: `0x18000b35d`
- name: `??1?$unique_ptr@VRemoteFileBrowseClient@@U?$default_delete@VRemoteFileBrowseClient@@@std@@@std@@QEAA@XZ`
- size: `105`
- prototype: `void __fastcall(char ***)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000b640`
- `0x180017b5c`

## callees

- `0x180002054`
- `0x18000591c`
- `0x18000b2f4`

## pseudocode

```c
void __fastcall std::unique_ptr<RemoteFileBrowseClient>::~unique_ptr<RemoteFileBrowseClient>(char ***a1)
{
  char **v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    std::wstring::~wstring(v1 + 25);
    std::wstring::~wstring(v1 + 21);
    std::wstring::~wstring(v1 + 17);
    std::wstring::~wstring(v1 + 13);
    std::wstring::~wstring(v1 + 9);
    std::wstring::~wstring(v1 + 5);
    std::wstring::~wstring(v1 + 1);
    operator delete(v1, 0xF0u);
  }
}

```

## disassembly

```asm
0x18000b2f4  push    rbx
0x18000b2f6  sub     rsp, 20h
0x18000b2fa  mov     rbx, [rcx]
0x18000b2fd  test    rbx, rbx
0x18000b300  jz      short loc_18000B357
0x18000b302  lea     rcx, [rbx+0C8h]
0x18000b309  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000b30e  lea     rcx, [rbx+0A8h]
0x18000b315  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000b31a  lea     rcx, [rbx+88h]
0x18000b321  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000b326  lea     rcx, [rbx+68h]
0x18000b32a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000b32f  lea     rcx, [rbx+48h]
0x18000b333  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000b338  lea     rcx, [rbx+28h]
0x18000b33c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000b341  lea     rcx, [rbx+8]
0x18000b345  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000b34a  mov     edx, 0F0h; unsigned __int64
0x18000b34f  mov     rcx, rbx; void *
0x18000b352  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b357  add     rsp, 20h
0x18000b35b  pop     rbx
0x18000b35c  retn
```
