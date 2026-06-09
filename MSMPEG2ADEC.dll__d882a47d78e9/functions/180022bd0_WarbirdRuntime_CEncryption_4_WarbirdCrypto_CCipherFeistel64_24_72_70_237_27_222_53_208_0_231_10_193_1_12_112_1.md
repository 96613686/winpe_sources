# WarbirdRuntime::CEncryption<4,WarbirdCrypto::CCipherFeistel64<24,72,70,237,27,222,53,208,0,231,10,193,1,12,112,144,6,198,107,101,2,235,80,186,11,157,72,94,22,222,54,40,18,175,45,86,26,120,120,203>,WarbirdCrypto::CHashFunctionSCP<1,3,1,2512323539126559255>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_5,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_5>::DoCrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_5 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_5 *,int)

- ea: `0x180022bd0`
- end: `0x180022ef1`
- name: `?DoCrypt@?$CEncryption@$03V?$CCipherFeistel64@$0BI@$0EI@$0EG@$0ON@$0BL@$0NO@$0DF@$0NA@$0A@$0OH@$09$0MB@$00$0M@$0HA@$0JA@$05$0MG@$0GL@$0GF@$01$0OL@$0FA@$0LK@$0L@$0JN@$0EI@$0FO@$0BG@$0NO@$0DG@$0CI@$0BC@$0KP@$0CN@$0FG@$0BK@$0HI@$0HI@$0ML@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$02$00$0CCNNJAPCKOHNKCBH@@2@UENCRYPTED_SEGMENT_DATA_CONST_5@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_5@5@@WarbirdRuntime@@CAJPEAUENCRYPTED_SEGMENT_DATA_CONST_5@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_5@2@H@Z`
- size: `801`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180020ca0`

## callees

- `0x1800017b0`
- `0x18001f500`
- `0x180020640`
- `0x180022bd0`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022ce0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022d67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022ea8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022ce0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022d67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022ea8`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180022cc6`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180022d4b`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180022e8e`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180022cc6`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180022d4b`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180022e8e`

## pseudocode

```c
__int64 WarbirdRuntime::CEncryption<4,WarbirdCrypto::CCipherFeistel64<24,72,70,237,27,222,53,208,0,231,10,193,1,12,112,144,6,198,107,101,2,235,80,186,11,157,72,94,22,222,54,40,18,175,45,86,26,120,120,203>,WarbirdCrypto::CHashFunctionSCP<1,3,1,2512323539126559255>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_5,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_5>::DoCrypt()
{
  return 0;
}

```

## disassembly

```asm
0x180022bd0  mov     r11, rsp
0x180022bd3  push    rbp
0x180022bd4  push    rdi
0x180022bd5  push    r13
0x180022bd7  push    r14
0x180022bd9  lea     rbp, [r11-5Fh]
0x180022bdd  sub     rsp, 0A8h
0x180022be4  mov     rax, cs:__security_cookie
0x180022beb  xor     rax, rsp
0x180022bee  mov     [rbp+57h+var_30], rax
0x180022bf2  mov     r8, cs:qword_1800A4958
0x180022bf9  xor     r13d, r13d
0x180022bfc  movzx   eax, r8b
0x180022c00  mov     r14d, r13d
0x180022c03  mov     [rbp+57h+var_58], rax
0x180022c07  mov     edi, r13d
0x180022c0a  mov     [rbp+57h+lpAddress], r13
0x180022c0e  mov     [rbp+57h+dwSize], r13
0x180022c12  mov     [rbp+57h+var_68], r13
0x180022c16  mov     [rbp+57h+var_60], r13d
0x180022c1a  mov     qword ptr [rbp+57h+flOldProtect], r13
0x180022c1e  test    r8d, 1FFFE00h
0x180022c25  jbe     loc_180022ED3
0x180022c2b  mov     [r11+8], rbx
0x180022c2f  lea     r9, __ImageBase
0x180022c36  mov     [r11+10h], rsi
0x180022c3a  mov     r10d, 8000h
0x180022c40  mov     [r11+18h], r12
0x180022c44  mov     [r11-28h], r15
0x180022c48  nop     dword ptr [rax+rax+00000000h]
0x180022c50  test    r14d, r14d
0x180022c53  js      loc_180022E4A
0x180022c59  mov     eax, edi
0x180022c5b  lea     rcx, ds:0[rax*8]
0x180022c63  mov     ebx, [rcx+r9+0A4960h]
0x180022c6b  lea     r12, [rcx+0A495Ch]
0x180022c72  mov     rcx, [rbp+57h+lpAddress]
0x180022c76  add     r12, r9
0x180022c79  and     ebx, 0FFFFFFFh
0x180022c7f  mov     esi, [r12]
0x180022c83  and     esi, 0FFFFFFFh
0x180022c89  add     rsi, r9
0x180022c8c  cmp     rsi, rcx
0x180022c8f  jb      short loc_180022CA2
0x180022c91  add     rcx, [rbp+57h+dwSize]
0x180022c95  lea     rdx, [rsi+rbx]; bool
0x180022c99  cmp     rdx, rcx
0x180022c9c  jb      loc_180022DAF
0x180022ca2  cmp     [rbp+57h+flOldProtect], r13d
0x180022ca6  jz      short loc_180022D0B
0x180022ca8  lea     rcx, [rbp+57h+var_48]; this
0x180022cac  call    ??0AutoEnableDynamicCodeGen@WarbirdRuntime@@QEAA@_N@Z; WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(bool)
0x180022cb1  mov     r8d, [rbp+57h+flOldProtect+4]
0x180022cb5  lea     r9, [rbp+57h+flOldProtect+4]; lpflOldProtect
0x180022cb9  mov     rdx, [rbp+57h+dwSize]; dwSize
0x180022cbd  bts     r8d, 1Eh; flNewProtect
0x180022cc2  mov     rcx, [rbp+57h+lpAddress]; lpAddress
0x180022cc6  call    cs:__imp_VirtualProtect
0x180022ccd  nop     dword ptr [rax+rax+00h]
0x180022cd2  mov     [rbp+57h+flOldProtect], r13d
0x180022cd6  cmp     [rbp+57h+var_38], r13b
0x180022cda  jz      short loc_180022D0B
0x180022cdc  mov     [rbp+57h+var_80], r13d
0x180022ce0  call    cs:__imp_GetCurrentThread
0x180022ce7  nop     dword ptr [rax+rax+00h]
0x180022cec  mov     r9d, 4
0x180022cf2  lea     r8, [rbp+57h+var_80]
0x180022cf6  mov     rcx, rax
0x180022cf9  mov     edx, 2
0x180022cfe  mov     rax, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x180022d05  call    cs:__guard_dispatch_icall_fptr
0x180022d0b  lea     rax, [rbx+0FFFh]
0x180022d12  mov     rcx, rsi
0x180022d15  and     rcx, 0FFFFFFFFFFFFF000h
0x180022d1c  add     rax, rsi
0x180022d1f  and     rax, 0FFFFFFFFFFFFF000h
0x180022d25  mov     [rbp+57h+lpAddress], rcx
0x180022d29  sub     rax, rcx
0x180022d2c  lea     rcx, [rbp+57h+var_48]; this
0x180022d30  mov     [rbp+57h+dwSize], rax
0x180022d34  call    ??0AutoEnableDynamicCodeGen@WarbirdRuntime@@QEAA@_N@Z; WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(bool)
0x180022d39  mov     rdx, [rbp+57h+dwSize]; dwSize
0x180022d3d  lea     r9, [rbp+57h+flOldProtect+4]; lpflOldProtect
0x180022d41  mov     rcx, [rbp+57h+lpAddress]; lpAddress
0x180022d45  mov     r8d, 40000040h; flNewProtect
0x180022d4b  call    cs:__imp_VirtualProtect
0x180022d52  nop     dword ptr [rax+rax+00h]
0x180022d57  mov     r15d, eax
0x180022d5a  mov     [rbp+57h+flOldProtect], eax
0x180022d5d  cmp     [rbp+57h+var_38], r13b
0x180022d61  jz      short loc_180022D92
0x180022d63  mov     [rbp+57h+var_80], r13d
0x180022d67  call    cs:__imp_GetCurrentThread
0x180022d6e  nop     dword ptr [rax+rax+00h]
0x180022d73  mov     r9d, 4
0x180022d79  lea     r8, [rbp+57h+var_80]
0x180022d7d  mov     rcx, rax
0x180022d80  mov     edx, 2
0x180022d85  mov     rax, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x180022d8c  call    cs:__guard_dispatch_icall_fptr
0x180022d92  mov     r8, cs:qword_1800A4958
0x180022d99  test    r15d, r15d
0x180022d9c  jz      loc_180022E24
0x180022da2  lea     r9, __ImageBase
0x180022da9  mov     r10d, 8000h
0x180022daf  mov     rcx, [rbp+57h+var_68]
0x180022db3  add     rcx, rsi
0x180022db6  jz      short loc_180022E24
0x180022db8  mov     eax, edi
0x180022dba  lea     r15, ds:0AD58Ch[rax*2]
0x180022dc2  add     r15, r9
0x180022dc5  movzx   r9d, word ptr [r15]
0x180022dc9  test    r10w, r9w
0x180022dcd  jz      short loc_180022E30
0x180022dcf  mov     eax, [r12]
0x180022dd3  movzx   edx, r9w
0x180022dd7  not     dx
0x180022dda  and     eax, 0FFFFFFFh
0x180022ddf  shr     edx, 9
0x180022de2  mov     r8, rbx
0x180022de5  and     edx, 1
0x180022de8  mov     [rsp+30h], edx
0x180022dec  mov     rdx, rcx
0x180022def  mov     byte ptr [rsp+0C0h+var_98], r9b
0x180022df4  mov     rcx, rsi
0x180022df7  mov     r9, cs:?g_EncryptedSegmentConstData_60@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_5@1@A; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_5 WarbirdRuntime::g_EncryptedSegmentConstData_60
0x180022dfe  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180022e02  call    ?Decrypt@?$CEncryption@$03V?$CCipherFeistel64@$0BI@$0EI@$0EG@$0ON@$0BL@$0NO@$0DF@$0NA@$0A@$0OH@$09$0MB@$00$0M@$0HA@$0JA@$05$0MG@$0GL@$0GF@$01$0OL@$0FA@$0LK@$0L@$0JN@$0EI@$0FO@$0BG@$0NO@$0DG@$0CI@$0BC@$0KP@$0CN@$0FG@$0BK@$0HI@$0HI@$0ML@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$02$00$0CCNNJAPCKOHNKCBH@@2@UENCRYPTED_SEGMENT_DATA_CONST_5@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_5@5@@WarbirdRuntime@@CAXPEBEPEAE_KTCKey@WarbirdCrypto@@KEH@Z; WarbirdRuntime::CEncryption<4,WarbirdCrypto::CCipherFeistel64<24,72,70,237,27,222,53,208,0,231,10,193,1,12,112,144,6,198,107,101,2,235,80,186,11,157,72,94,22,222,54,40,18,175,45,86,26,120,120,203>,WarbirdCrypto::CHashFunctionSCP<1,3,1,2512323539126559255>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_5,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_5>::Decrypt(uchar const *,uchar *,unsigned __int64,WarbirdCrypto::CKey,ulong,uchar,int)
0x180022e07  movzx   eax, word ptr [r15]
0x180022e0b  mov     ecx, 7DFFh
0x180022e10  mov     r8, cs:qword_1800A4958
0x180022e17  and     ax, cx
0x180022e1a  or      ax, 200h
0x180022e1e  mov     [r15], ax
0x180022e22  jmp     short loc_180022E2A
0x180022e24  mov     r14d, 8007000Eh
0x180022e2a  mov     r10d, 8000h
0x180022e30  mov     eax, r8d
0x180022e33  lea     r9, __ImageBase
0x180022e3a  shr     eax, 9
0x180022e3d  inc     edi
0x180022e3f  movzx   eax, ax
0x180022e42  cmp     edi, eax
0x180022e44  jb      loc_180022C50
0x180022e4a  mov     r15, [rsp+0A0h]
0x180022e52  mov     r12, [rsp+0C0h+arg_10]
0x180022e5a  mov     rsi, [rsp+0C0h+arg_8]
0x180022e62  mov     rbx, [rsp+0C0h+arg_0]
0x180022e6a  cmp     [rbp+57h+flOldProtect], r13d
0x180022e6e  jz      short loc_180022ED3
0x180022e70  lea     rcx, [rbp+57h+var_48]; this
0x180022e74  call    ??0AutoEnableDynamicCodeGen@WarbirdRuntime@@QEAA@_N@Z; WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(bool)
0x180022e79  mov     r8d, [rbp+57h+flOldProtect+4]
0x180022e7d  lea     r9, [rbp+57h+flOldProtect+4]; lpflOldProtect
0x180022e81  mov     rdx, [rbp+57h+dwSize]; dwSize
0x180022e85  bts     r8d, 1Eh; flNewProtect
0x180022e8a  mov     rcx, [rbp+57h+lpAddress]; lpAddress
0x180022e8e  call    cs:__imp_VirtualProtect
0x180022e95  nop     dword ptr [rax+rax+00h]
0x180022e9a  mov     [rbp+57h+flOldProtect], r13d
0x180022e9e  cmp     [rbp+57h+var_38], r13b
0x180022ea2  jz      short loc_180022ED3
0x180022ea4  mov     [rbp+57h+var_80], r13d
0x180022ea8  call    cs:__imp_GetCurrentThread
0x180022eaf  nop     dword ptr [rax+rax+00h]
0x180022eb4  mov     r9d, 4
0x180022eba  lea     r8, [rbp+57h+var_80]
0x180022ebe  mov     rcx, rax
0x180022ec1  mov     edx, 2
0x180022ec6  mov     rax, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x180022ecd  call    cs:__guard_dispatch_icall_fptr
0x180022ed3  mov     eax, r14d
0x180022ed6  mov     rcx, [rbp+57h+var_30]
0x180022eda  xor     rcx, rsp; StackCookie
0x180022edd  call    __security_check_cookie
0x180022ee2  add     rsp, 0A8h
0x180022ee9  pop     r14
0x180022eeb  pop     r13
0x180022eed  pop     rdi
0x180022eee  pop     rbp
0x180022eef  retn
```
