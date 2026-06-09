# WarbirdRuntime::CEncryption<5,WarbirdCrypto::CCipherFeistel64<28,217,204,126,13,48,223,208,17,214,202,223,18,190,165,137,8,173,218,252,11,62,167,189,14,93,32,35,30,91,149,35,2,231,74,182,24,237,126,169>,WarbirdCrypto::CHashFunctionSCP<1,1,2,2329519407998533220>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6>::DoCrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6 *,int)

- ea: `0x180022f00`
- end: `0x1800232c0`
- name: `?DoCrypt@?$CEncryption@$04V?$CCipherFeistel64@$0BM@$0NJ@$0MM@$0HO@$0N@$0DA@$0NP@$0NA@$0BB@$0NG@$0MK@$0NP@$0BC@$0LO@$0KF@$0IJ@$07$0KN@$0NK@$0PM@$0L@$0DO@$0KH@$0LN@$0O@$0FN@$0CA@$0CD@$0BO@$0FL@$0JF@$0CD@$01$0OH@$0EK@$0LG@$0BI@$0ON@$0HO@$0KJ@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$00$01$0CAFEBNIPCLCBHOGE@@2@UENCRYPTED_SEGMENT_DATA_CONST_6@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_6@5@@WarbirdRuntime@@CAJPEAUENCRYPTED_SEGMENT_DATA_CONST_6@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_6@2@H@Z`
- size: `960`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180021310`
- `0x180024700`

## callees

- `0x1800017b0`
- `0x18001f500`
- `0x180020d30`
- `0x180022f00`
- `0x180024320`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023020`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800230aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023275`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023020`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800230aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023275`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180023006`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18002308b`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18002325b`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180023006`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18002308b`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18002325b`

## pseudocode

```c
__int64 WarbirdRuntime::CEncryption<5,WarbirdCrypto::CCipherFeistel64<28,217,204,126,13,48,223,208,17,214,202,223,18,190,165,137,8,173,218,252,11,62,167,189,14,93,32,35,30,91,149,35,2,231,74,182,24,237,126,169>,WarbirdCrypto::CHashFunctionSCP<1,1,2,2329519407998533220>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6>::DoCrypt()
{
  return 0;
}

```

## disassembly

```asm
0x180022f00  push    rbp
0x180022f02  push    rsi
0x180022f03  push    r13
0x180022f05  push    r14
0x180022f07  push    r15
0x180022f09  lea     rbp, [rsp-37h]
0x180022f0e  sub     rsp, 0A0h
0x180022f15  mov     rax, cs:__security_cookie
0x180022f1c  xor     rax, rsp
0x180022f1f  mov     [rbp+57h+var_30], rax
0x180022f23  mov     r10, cs:qword_1800A49C0
0x180022f2a  xor     r14d, r14d
0x180022f2d  movzx   eax, r10b
0x180022f31  mov     r13d, r8d
0x180022f34  mov     [rbp+57h+var_58], rax
0x180022f38  mov     r15d, r14d
0x180022f3b  mov     [rbp+57h+lpAddress], r14
0x180022f3f  mov     esi, r14d
0x180022f42  mov     [rbp+57h+dwSize], r14
0x180022f46  mov     [rbp+57h+var_68], r14
0x180022f4a  mov     [rbp+57h+var_60], r8d
0x180022f4e  mov     qword ptr [rbp+57h+flOldProtect], r14
0x180022f52  test    r10d, 0FFFF00h
0x180022f59  jbe     loc_1800232A0
0x180022f5f  mov     r9, cs:qword_1800A49B8
0x180022f66  lea     r8, __ImageBase
0x180022f6d  mov     [rsp+0C0h+arg_0], rbx
0x180022f75  mov     r11d, 8000h
0x180022f7b  mov     [rsp+0C0h+arg_8], rdi
0x180022f83  mov     [rsp+0C0h+arg_10], r12
0x180022f8b  nop     dword ptr [rax+rax+00h]
0x180022f90  test    r15d, r15d
0x180022f93  js      loc_18002321F
0x180022f99  mov     rcx, [rbp+57h+lpAddress]
0x180022f9d  mov     eax, esi
0x180022f9f  lea     rbx, ds:0[rax*8]
0x180022fa7  lea     r12, [rbx+0A49C4h]
0x180022fae  mov     ebx, [rbx+r8+0A49C8h]
0x180022fb6  add     r12, r8
0x180022fb9  and     ebx, 0FFFFFFFh
0x180022fbf  mov     edi, [r12]
0x180022fc3  and     edi, 0FFFFFFFh
0x180022fc9  add     rdi, r8
0x180022fcc  cmp     rdi, rcx
0x180022fcf  jb      short loc_180022FE2
0x180022fd1  add     rcx, [rbp+57h+dwSize]
0x180022fd5  lea     rdx, [rbx+rdi]; bool
0x180022fd9  cmp     rdx, rcx
0x180022fdc  jb      loc_1800230F9
0x180022fe2  cmp     [rbp+57h+flOldProtect], 0
0x180022fe6  jz      short loc_18002304B
0x180022fe8  lea     rcx, [rbp+57h+var_48]; this
0x180022fec  call    ??0AutoEnableDynamicCodeGen@WarbirdRuntime@@QEAA@_N@Z; WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(bool)
0x180022ff1  mov     r8d, [rbp+57h+flOldProtect+4]
0x180022ff5  lea     r9, [rbp+57h+flOldProtect+4]; lpflOldProtect
0x180022ff9  mov     rdx, [rbp+57h+dwSize]; dwSize
0x180022ffd  bts     r8d, 1Eh; flNewProtect
0x180023002  mov     rcx, [rbp+57h+lpAddress]; lpAddress
0x180023006  call    cs:__imp_VirtualProtect
0x18002300d  nop     dword ptr [rax+rax+00h]
0x180023012  cmp     [rbp+57h+var_38], 0
0x180023016  mov     [rbp+57h+flOldProtect], r14d
0x18002301a  jz      short loc_18002304B
0x18002301c  mov     [rbp+57h+var_7C], r14d
0x180023020  call    cs:__imp_GetCurrentThread
0x180023027  nop     dword ptr [rax+rax+00h]
0x18002302c  mov     r9d, 4
0x180023032  lea     r8, [rbp+57h+var_7C]
0x180023036  mov     rcx, rax
0x180023039  mov     edx, 2
0x18002303e  mov     rax, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x180023045  call    cs:__guard_dispatch_icall_fptr
0x18002304b  lea     rax, [rbx+0FFFh]
0x180023052  mov     rcx, rdi
0x180023055  and     rcx, 0FFFFFFFFFFFFF000h
0x18002305c  add     rax, rdi
0x18002305f  and     rax, 0FFFFFFFFFFFFF000h
0x180023065  mov     [rbp+57h+lpAddress], rcx
0x180023069  sub     rax, rcx
0x18002306c  lea     rcx, [rbp+57h+var_48]; this
0x180023070  mov     [rbp+57h+dwSize], rax
0x180023074  call    ??0AutoEnableDynamicCodeGen@WarbirdRuntime@@QEAA@_N@Z; WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(bool)
0x180023079  mov     rdx, [rbp+57h+dwSize]; dwSize
0x18002307d  lea     r9, [rbp+57h+flOldProtect+4]; lpflOldProtect
0x180023081  mov     rcx, [rbp+57h+lpAddress]; lpAddress
0x180023085  mov     r8d, 40000040h; flNewProtect
0x18002308b  call    cs:__imp_VirtualProtect
0x180023092  nop     dword ptr [rax+rax+00h]
0x180023097  cmp     [rbp+57h+var_38], 0
0x18002309b  mov     r14d, eax
0x18002309e  mov     [rbp+57h+flOldProtect], eax
0x1800230a1  jz      short loc_1800230D5
0x1800230a3  mov     [rbp+57h+var_7C], 0
0x1800230aa  call    cs:__imp_GetCurrentThread
0x1800230b1  nop     dword ptr [rax+rax+00h]
0x1800230b6  mov     r9d, 4
0x1800230bc  lea     r8, [rbp+57h+var_7C]
0x1800230c0  mov     rcx, rax
0x1800230c3  mov     edx, 2
0x1800230c8  mov     rax, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x1800230cf  call    cs:__guard_dispatch_icall_fptr
0x1800230d5  mov     r10, cs:qword_1800A49C0
0x1800230dc  mov     r9, cs:qword_1800A49B8
0x1800230e3  test    r14d, r14d
0x1800230e6  jz      loc_1800231F3
0x1800230ec  lea     r8, __ImageBase
0x1800230f3  mov     r11d, 8000h
0x1800230f9  mov     rdx, [rbp+57h+var_68]
0x1800230fd  add     rdx, rdi
0x180023100  jz      loc_1800231F3
0x180023106  mov     eax, esi
0x180023108  lea     r14, [rax+rax]
0x18002310c  test    r13d, r13d
0x18002310f  jz      short loc_18002317B
0x180023111  cmp     word ptr [r14+r8+0AD594h], 0
0x18002311b  jl      loc_180023206
0x180023121  mov     eax, [r12]
0x180023125  lea     rcx, [rbp+57h+var_80]
0x180023129  mov     [rsp+0C0h+var_98], rcx
0x18002312e  and     eax, 0FFFFFFFh
0x180023133  mov     rcx, rdi
0x180023136  mov     [rsp+0C0h+var_A0], eax
0x18002313a  mov     r8, rbx
0x18002313d  mov     [rbp+57h+var_80], 0
0x180023141  call    ?Encrypt@?$CEncryption@$04V?$CCipherFeistel64@$0BM@$0NJ@$0MM@$0HO@$0N@$0DA@$0NP@$0NA@$0BB@$0NG@$0MK@$0NP@$0BC@$0LO@$0KF@$0IJ@$07$0KN@$0NK@$0PM@$0L@$0DO@$0KH@$0LN@$0O@$0FN@$0CA@$0CD@$0BO@$0FL@$0JF@$0CD@$01$0OH@$0EK@$0LG@$0BI@$0ON@$0HO@$0KJ@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$00$01$0CAFEBNIPCLCBHOGE@@2@UENCRYPTED_SEGMENT_DATA_CONST_6@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_6@5@@WarbirdRuntime@@CAXPEBEPEAE_KTCKey@WarbirdCrypto@@K1@Z; WarbirdRuntime::CEncryption<5,WarbirdCrypto::CCipherFeistel64<28,217,204,126,13,48,223,208,17,214,202,223,18,190,165,137,8,173,218,252,11,62,167,189,14,93,32,35,30,91,149,35,2,231,74,182,24,237,126,169>,WarbirdCrypto::CHashFunctionSCP<1,1,2,2329519407998533220>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6>::Encrypt(uchar const *,uchar *,unsigned __int64,WarbirdCrypto::CKey,ulong,uchar *)
0x180023146  movzx   eax, [rbp+57h+var_80]
0x18002314a  lea     r8, __ImageBase
0x180023151  mov     r10, cs:qword_1800A49C0
0x180023158  mov     r11d, 8000h
0x18002315e  mov     r9, cs:qword_1800A49B8
0x180023165  mov     [r14+r8+0AD594h], al
0x18002316d  or      [r14+r8+0AD594h], r11w
0x180023176  jmp     loc_180023206
0x18002317b  movzx   r8d, word ptr [r14+r8+0AD594h]
0x180023184  test    r11w, r8w
0x180023188  jz      short loc_1800231FF
0x18002318a  mov     eax, [r12]
0x18002318e  movzx   ecx, r8w
0x180023192  not     cx
0x180023195  and     eax, 0FFFFFFFh
0x18002319a  shr     ecx, 8
0x18002319d  and     ecx, 1
0x1800231a0  mov     [rsp+0C0h+var_90], ecx
0x1800231a4  mov     rcx, rdi
0x1800231a7  mov     byte ptr [rsp+0C0h+var_98], r8b
0x1800231ac  mov     r8, rbx
0x1800231af  mov     [rsp+0C0h+var_A0], eax
0x1800231b3  call    ?Decrypt@?$CEncryption@$04V?$CCipherFeistel64@$0BM@$0NJ@$0MM@$0HO@$0N@$0DA@$0NP@$0NA@$0BB@$0NG@$0MK@$0NP@$0BC@$0LO@$0KF@$0IJ@$07$0KN@$0NK@$0PM@$0L@$0DO@$0KH@$0LN@$0O@$0FN@$0CA@$0CD@$0BO@$0FL@$0JF@$0CD@$01$0OH@$0EK@$0LG@$0BI@$0ON@$0HO@$0KJ@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$00$01$0CAFEBNIPCLCBHOGE@@2@UENCRYPTED_SEGMENT_DATA_CONST_6@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_6@5@@WarbirdRuntime@@CAXPEBEPEAE_KTCKey@WarbirdCrypto@@KEH@Z; WarbirdRuntime::CEncryption<5,WarbirdCrypto::CCipherFeistel64<28,217,204,126,13,48,223,208,17,214,202,223,18,190,165,137,8,173,218,252,11,62,167,189,14,93,32,35,30,91,149,35,2,231,74,182,24,237,126,169>,WarbirdCrypto::CHashFunctionSCP<1,1,2,2329519407998533220>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6>::Decrypt(uchar const *,uchar *,unsigned __int64,WarbirdCrypto::CKey,ulong,uchar,int)
0x1800231b8  mov     r10, cs:qword_1800A49C0
0x1800231bf  lea     r8, __ImageBase
0x1800231c6  movzx   eax, word ptr [r14+r8+0AD594h]
0x1800231cf  mov     ecx, 7EFFh
0x1800231d4  mov     r9, cs:qword_1800A49B8
0x1800231db  and     ax, cx
0x1800231de  or      ax, 100h
0x1800231e2  mov     r11d, 8000h
0x1800231e8  mov     [r14+r8+0AD594h], ax
0x1800231f1  jmp     short loc_180023206
0x1800231f3  mov     r15d, 8007000Eh
0x1800231f9  mov     r11d, 8000h
0x1800231ff  lea     r8, __ImageBase
0x180023206  mov     eax, r10d
0x180023209  inc     esi
0x18002320b  shr     eax, 8
0x18002320e  mov     r14d, 0
0x180023214  movzx   eax, ax
0x180023217  cmp     esi, eax
0x180023219  jb      loc_180022F90
0x18002321f  cmp     [rbp+57h+flOldProtect], 0
0x180023223  mov     r12, [rsp+0C0h+arg_10]
0x18002322b  mov     rdi, [rsp+0C0h+arg_8]
0x180023233  mov     rbx, [rsp+0C0h+arg_0]
0x18002323b  jz      short loc_1800232A0
0x18002323d  lea     rcx, [rbp+57h+var_48]; this
0x180023241  call    ??0AutoEnableDynamicCodeGen@WarbirdRuntime@@QEAA@_N@Z; WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(bool)
0x180023246  mov     r8d, [rbp+57h+flOldProtect+4]
0x18002324a  lea     r9, [rbp+57h+flOldProtect+4]; lpflOldProtect
0x18002324e  mov     rdx, [rbp+57h+dwSize]; dwSize
0x180023252  bts     r8d, 1Eh; flNewProtect
0x180023257  mov     rcx, [rbp+57h+lpAddress]; lpAddress
0x18002325b  call    cs:__imp_VirtualProtect
0x180023262  nop     dword ptr [rax+rax+00h]
0x180023267  cmp     [rbp+57h+var_38], 0
0x18002326b  mov     [rbp+57h+flOldProtect], r14d
0x18002326f  jz      short loc_1800232A0
0x180023271  mov     [rbp+57h+var_7C], r14d
0x180023275  call    cs:__imp_GetCurrentThread
0x18002327c  nop     dword ptr [rax+rax+00h]
0x180023281  mov     r9d, 4
0x180023287  lea     r8, [rbp+57h+var_7C]
0x18002328b  mov     rcx, rax
0x18002328e  mov     edx, 2
0x180023293  mov     rax, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x18002329a  call    cs:__guard_dispatch_icall_fptr
0x1800232a0  mov     eax, r15d
0x1800232a3  mov     rcx, [rbp+57h+var_30]
0x1800232a7  xor     rcx, rsp; StackCookie
0x1800232aa  call    __security_check_cookie
0x1800232af  add     rsp, 0A0h
0x1800232b6  pop     r15
0x1800232b8  pop     r14
0x1800232ba  pop     r13
0x1800232bc  pop     rsi
0x1800232bd  pop     rbp
0x1800232be  retn
```
