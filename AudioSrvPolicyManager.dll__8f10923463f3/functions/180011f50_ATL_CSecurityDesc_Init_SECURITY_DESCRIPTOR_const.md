# ATL::CSecurityDesc::Init(_SECURITY_DESCRIPTOR const &)

- ea: `0x180011f50`
- end: `0x180012066`
- name: `?Init@CSecurityDesc@ATL@@IEAAXAEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `278`
- prototype: `void(ATL::CSecurityDesc *__hidden this, const struct _SECURITY_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001039c`

## callees

- `0x180011d78`
- `0x180011f50`
- `0x18002bd9c`
- `0x18002ccf0`
- `0x180032736`
- `0x1800327e0`
- `0x1800327f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180011fba`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012050`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180011fba`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012050`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180011f77`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180011f77`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001200c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001200c`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18001203b`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18001203b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180011f6b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180011f6b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180011fa5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180011fa5`

## pseudocode

```c

```

## disassembly

```asm
0x180011f50  mov     [rsp+arg_18], rbx
0x180011f55  push    rdi
0x180011f56  sub     rsp, 20h
0x180011f5a  mov     rdi, rcx
0x180011f5d  mov     [rsp+28h+dwRevision], 0
0x180011f65  mov     rcx, rdx; pSecurityDescriptor
0x180011f68  mov     rbx, rdx
0x180011f6b  call    cs:__imp_GetSecurityDescriptorLength
0x180011f71  mov     ecx, eax; Size
0x180011f73  mov     dword ptr [rsp+28h+Size], ecx
0x180011f77  call    cs:__imp_malloc
0x180011f7d  mov     [rdi+8], rax
0x180011f81  test    rax, rax
0x180011f84  jnz     short loc_180011F91
0x180011f86  mov     ecx, 8007000Eh; int
0x180011f8b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011f91  xor     eax, eax
0x180011f93  lea     r8, [rsp+28h+dwRevision]; lpdwRevision
0x180011f98  lea     rdx, [rsp+28h+pControl]; pControl
0x180011f9d  mov     [rsp+28h+pControl], ax
0x180011fa2  mov     rcx, rbx; pSecurityDescriptor
0x180011fa5  call    cs:__imp_GetSecurityDescriptorControl
0x180011fab  test    eax, eax
0x180011fad  jnz     short loc_180011FD0
0x180011faf  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180011fb4  mov     rcx, [rdi+8]; Block
0x180011fb8  mov     ebx, eax
0x180011fba  call    cs:__imp_free
0x180011fc0  mov     ecx, ebx; int
0x180011fc2  mov     qword ptr [rdi+8], 0
0x180011fca  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011fd0  mov     rax, [rdi+8]
0x180011fd4  mov     ecx, 8000h
0x180011fd9  test    [rsp+28h+pControl], cx
0x180011fde  jz      short loc_180012030
0x180011fe0  mov     r8d, dword ptr [rsp+28h+Size]; Size
0x180011fe5  test    r8, r8
0x180011fe8  jnz     short loc_180011FEE
0x180011fea  xor     ebx, ebx
0x180011fec  jmp     short loc_18001201E
0x180011fee  test    rax, rax
0x180011ff1  jz      short loc_18001200C
0x180011ff3  mov     rcx, rax; void *
0x180011ff6  test    rbx, rbx
0x180011ff9  jz      short loc_180012005
0x180011ffb  mov     rdx, rbx; Src
0x180011ffe  call    memcpy_0
0x180012003  jmp     short loc_180011FEA
0x180012005  xor     edx, edx; Val
0x180012007  call    memset_0
0x18001200c  call    cs:__imp__o__errno
0x180012012  mov     ebx, 16h
0x180012017  mov     [rax], ebx
0x180012019  call    _invalid_parameter_noinfo
0x18001201e  mov     ecx, ebx; int
0x180012020  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180012025  mov     rbx, [rsp+28h+arg_18]
0x18001202a  add     rsp, 20h
0x18001202e  pop     rdi
0x18001202f  retn
0x180012030  lea     r8, [rsp+28h+Size]; lpdwBufferLength
0x180012035  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x180012038  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x18001203b  call    cs:__imp_MakeSelfRelativeSD
0x180012041  test    eax, eax
0x180012043  jnz     short loc_180012025
0x180012045  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001204a  mov     rcx, [rdi+8]; Block
0x18001204e  mov     ebx, eax
0x180012050  call    cs:__imp_free
0x180012056  mov     ecx, ebx; int
0x180012058  mov     qword ptr [rdi+8], 0
0x180012060  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
