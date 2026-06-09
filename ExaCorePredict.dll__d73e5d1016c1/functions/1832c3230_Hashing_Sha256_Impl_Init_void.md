# Hashing::Sha256::Impl::Init(void)

- ea: `0x1832c3230`
- end: `0x1832c335c`
- name: `?Init@Impl@Sha256@Hashing@@QEAAXXZ`
- size: `300`
- prototype: `void __fastcall(Hashing::Sha256::Impl *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1832c3360`

## callees

- `0x182dbf780`
- `0x182dbf7f0`
- `0x182dc2100`
- `0x1832c2fc0`
- `0x1832c3230`
- `0x1832c3370`
- `0x1832dbe96`

## import_xrefs

- `ADVAPI32!CryptCreateHash` at `0x1832c32eb`
- `ADVAPI32!CryptCreateHash` at `0x1832c32eb`
- `ADVAPI32!CryptAcquireContextA` at `0x1832c326d`
- `ADVAPI32!CryptAcquireContextA` at `0x1832c326d`

## string_xrefs

- `0x1832c3306`: `Failed creating SHA256 object [CryptCreateHash: `

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Hashing::Sha256::Impl::Init(Hashing::Sha256::Impl *this)
{
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-88h] BYREF
  __int64 v9; // [rsp+48h] [rbp-70h]
  _BYTE v10[32]; // [rsp+50h] [rbp-68h] BYREF
  _BYTE v11[32]; // [rsp+70h] [rbp-48h] BYREF
  _BYTE v12[40]; // [rsp+90h] [rbp-28h] BYREF

  v9 = -2;
  if ( *((_DWORD *)this + 4) )
    Hashing::ThrowBadState(0);
  if ( !*(_QWORD *)this && !CryptAcquireContextA((HCRYPTPROV *)this, 0, 0, 0x18u, 0xF0000040) )
  {
    v2 = Hashing::ErrorString(v10);
    v3 = std::operator+<char>(v11, "Failed acquiring hash context [CryptAcquireContext: ", v2);
    v4 = std::operator+<char>(v12, v3, "]");
    std::runtime_error::runtime_error(pExceptionObject, v4);
    throw (std::runtime_error *)pExceptionObject;
  }
  if ( !*((_QWORD *)this + 1) && !CryptCreateHash(*(_QWORD *)this, 0x800Cu, 0, 0, (HCRYPTHASH *)this + 1) )
  {
    v5 = Hashing::ErrorString(v12);
    v6 = std::operator+<char>(v11, "Failed creating SHA256 object [CryptCreateHash: ", v5);
    v7 = std::operator+<char>(v10, v6, "]");
    std::runtime_error::runtime_error(pExceptionObject, v7);
    throw (std::runtime_error *)pExceptionObject;
  }
  *((_DWORD *)this + 4) = 1;
}

```

## disassembly

```asm
0x1832c3230  push    rbx
0x1832c3232  sub     rsp, 0B0h
0x1832c3239  mov     [rsp+0B8h+var_70], 0FFFFFFFFFFFFFFFEh
0x1832c3242  mov     rbx, rcx
0x1832c3245  mov     edx, [rcx+10h]
0x1832c3248  test    edx, edx
0x1832c324a  jz      short loc_1832C3254
0x1832c324c  xor     ecx, ecx
0x1832c324e  call    Hashing__ThrowBadState
0x1832c3254  cmp     qword ptr [rcx], 0
0x1832c3258  jnz     short loc_1832C32CE
0x1832c325a  mov     [rsp+0B8h+dwFlags], 0F0000040h; dwFlags
0x1832c3262  mov     r9d, 18h; dwProvType
0x1832c3268  xor     r8d, r8d; szProvider
0x1832c326b  xor     edx, edx; szContainer
0x1832c326d  call    cs:__imp_CryptAcquireContextA
0x1832c3273  test    eax, eax
0x1832c3275  jnz     short loc_1832C32CE
0x1832c3277  lea     rcx, [rsp+0B8h+var_68]
0x1832c327c  call    Hashing__ErrorString
0x1832c3281  nop
0x1832c3282  mov     r8, rax
0x1832c3285  lea     rdx, aFailedAcquirin; "Failed acquiring hash context [CryptAcq"...
0x1832c328c  lea     rcx, [rsp+0B8h+var_48]
0x1832c3291  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@PEBD$$QEAV10@@Z; std::operator+<char>(char const *,std::string &&)
0x1832c3296  nop
0x1832c3297  lea     r8, asc_18338F7E4; "]"
0x1832c329e  mov     rdx, rax
0x1832c32a1  lea     rcx, [rsp+0B8h+var_28]
0x1832c32a9  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@PEBD@Z; std::operator+<char>(std::string &&,char const *)
0x1832c32ae  nop
0x1832c32af  mov     rdx, rax
0x1832c32b2  lea     rcx, [rsp+0B8h+pExceptionObject]
0x1832c32b7  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x1832c32bc  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1832c32c3  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x1832c32c8  call    _CxxThrowException_0
0x1832c32ce  lea     rax, [rbx+8]
0x1832c32d2  cmp     qword ptr [rax], 0
0x1832c32d6  jnz     short loc_1832C334C
0x1832c32d8  mov     qword ptr [rsp+0B8h+dwFlags], rax; phHash
0x1832c32dd  xor     r9d, r9d; dwFlags
0x1832c32e0  xor     r8d, r8d; hKey
0x1832c32e3  mov     edx, 800Ch; Algid
0x1832c32e8  mov     rcx, [rbx]; hProv
0x1832c32eb  call    cs:__imp_CryptCreateHash
0x1832c32f1  test    eax, eax
0x1832c32f3  jnz     short loc_1832C334C
0x1832c32f5  lea     rcx, [rsp+0B8h+var_28]
0x1832c32fd  call    Hashing__ErrorString
0x1832c3302  nop
0x1832c3303  mov     r8, rax
0x1832c3306  lea     rdx, aFailedCreating; "Failed creating SHA256 object [CryptCre"...
0x1832c330d  lea     rcx, [rsp+0B8h+var_48]
0x1832c3312  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@PEBD$$QEAV10@@Z; std::operator+<char>(char const *,std::string &&)
0x1832c3317  nop
0x1832c3318  lea     r8, asc_18338F7E4; "]"
0x1832c331f  mov     rdx, rax
0x1832c3322  lea     rcx, [rsp+0B8h+var_68]
0x1832c3327  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@PEBD@Z; std::operator+<char>(std::string &&,char const *)
0x1832c332c  nop
0x1832c332d  mov     rdx, rax
0x1832c3330  lea     rcx, [rsp+0B8h+pExceptionObject]
0x1832c3335  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x1832c333a  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1832c3341  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x1832c3346  call    _CxxThrowException_0
0x1832c334c  mov     dword ptr [rbx+10h], 1
0x1832c3353  add     rsp, 0B0h
0x1832c335a  pop     rbx
0x1832c335b  retn
```
