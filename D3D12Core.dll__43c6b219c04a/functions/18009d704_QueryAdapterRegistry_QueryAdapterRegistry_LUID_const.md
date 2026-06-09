# QueryAdapterRegistry::QueryAdapterRegistry(_LUID const &)

- ea: `0x18009d704`
- end: `0x18009d7f9`
- name: `??0QueryAdapterRegistry@@QEAA@AEBU_LUID@@@Z`
- size: `245`
- prototype: `QueryAdapterRegistry *__fastcall(QueryAdapterRegistry *__hidden this, const struct _LUID *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18009ba98`
- `0x18012a490`

## callees

- `0x18000b010`
- `0x18009d704`
- `0x18009d800`
- `0x1800bb480`
- `0x1800bc094`

## import_xrefs

- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTQueryAdapterInfo` at `0x18009d7c3`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTQueryAdapterInfo` at `0x18009d7c3`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTOpenAdapterFromLuid` at `0x18009d76a`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTOpenAdapterFromLuid` at `0x18009d76a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
QueryAdapterRegistry *__fastcall QueryAdapterRegistry::QueryAdapterRegistry(
        QueryAdapterRegistry *this,
        const struct _LUID *a2)
{
  int v4; // eax
  _BYTE v6[8]; // [rsp+20h] [rbp-50h] BYREF
  _DWORD v7[2]; // [rsp+28h] [rbp-48h] BYREF
  char *v8; // [rsp+30h] [rbp-40h]
  __int64 v9; // [rsp+38h] [rbp-38h]
  QueryAdapterRegistry *v10; // [rsp+40h] [rbp-30h]
  struct _LUID v11; // [rsp+50h] [rbp-20h] BYREF
  int v12; // [rsp+58h] [rbp-18h]

  v10 = this;
  v6[0] = 0;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  std::vector<unsigned char>::_Construct_n<unsigned char const &>(this, a2, v6);
  *((_QWORD *)this + 3) = *(_QWORD *)this;
  v11 = *a2;
  v12 = 0;
  v4 = D3DKMTOpenAdapterFromLuid(&v11);
  if ( v4 < 0 )
    ThrowFailure(v4 | 0x10000000);
  *((_DWORD *)this + 8) = v12;
  *((_DWORD *)this + 9) = -1073741772;
  *((_QWORD *)this + 5) = 0;
  memset_0((char *)this + 48, 0, 0x50u);
  v7[0] = *((_DWORD *)this + 8);
  v7[1] = 60;
  v8 = (char *)this + 48;
  v9 = 80;
  if ( (int)D3DKMTQueryAdapterInfo(v7) < 0 )
    ThrowFailure(-2147467259);
  return this;
}

```

## disassembly

```asm
0x18009d704  mov     [rsp-8+arg_10], rbx
0x18009d709  mov     [rsp-8+arg_18], rdi
0x18009d70e  push    rbp
0x18009d70f  mov     rbp, rsp
0x18009d712  sub     rsp, 70h
0x18009d716  mov     rax, cs:__security_cookie
0x18009d71d  xor     rax, rsp
0x18009d720  mov     [rbp+var_10], rax
0x18009d724  mov     rbx, rdx
0x18009d727  mov     rdi, rcx
0x18009d72a  mov     [rbp+var_30], rcx
0x18009d72e  mov     [rbp+var_50], 0
0x18009d732  mov     qword ptr [rcx], 0
0x18009d739  mov     qword ptr [rcx+8], 0
0x18009d741  mov     qword ptr [rcx+10h], 0
0x18009d749  lea     r8, [rbp+var_50]
0x18009d74d  call    ??$_Construct_n@AEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBE@Z; std::vector<uchar>::_Construct_n<uchar const &>(unsigned __int64,uchar const &)
0x18009d752  nop
0x18009d753  mov     rax, [rdi]
0x18009d756  mov     [rdi+18h], rax
0x18009d75a  mov     rax, [rbx]
0x18009d75d  mov     [rbp+var_20], rax
0x18009d761  xor     eax, eax
0x18009d763  mov     [rbp+var_18], eax
0x18009d766  lea     rcx, [rbp+var_20]
0x18009d76a  call    cs:__imp_D3DKMTOpenAdapterFromLuid
0x18009d770  test    eax, eax
0x18009d772  jns     short loc_18009D77F
0x18009d774  bts     eax, 1Ch
0x18009d778  mov     ecx, eax; int
0x18009d77a  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18009d77f  mov     eax, [rbp+var_18]
0x18009d782  mov     [rdi+20h], eax
0x18009d785  mov     dword ptr [rdi+24h], 0C0000034h
0x18009d78c  mov     qword ptr [rdi+28h], 0
0x18009d794  lea     rbx, [rdi+30h]
0x18009d798  xor     edx, edx; Val
0x18009d79a  lea     r8d, [rdx+50h]; Size
0x18009d79e  mov     rcx, rbx; void *
0x18009d7a1  call    memset_0
0x18009d7a6  mov     eax, [rdi+20h]
0x18009d7a9  mov     [rbp+var_48], eax
0x18009d7ac  mov     [rbp+var_44], 3Ch ; '<'
0x18009d7b3  mov     [rbp+var_40], rbx
0x18009d7b7  mov     [rbp+var_38], 50h ; 'P'
0x18009d7bf  lea     rcx, [rbp+var_48]
0x18009d7c3  call    cs:__imp_D3DKMTQueryAdapterInfo
0x18009d7c9  test    eax, eax
0x18009d7cb  jns     short loc_18009D7D8
0x18009d7cd  mov     ecx, 80004005h; int
0x18009d7d2  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18009d7d7  nop
0x18009d7d8  mov     rax, rdi
0x18009d7db  mov     rcx, [rbp+var_10]
0x18009d7df  xor     rcx, rsp; StackCookie
0x18009d7e2  call    __security_check_cookie
0x18009d7e7  lea     r11, [rsp+70h+var_s0]
0x18009d7ec  mov     rbx, [r11+20h]
0x18009d7f0  mov     rdi, [r11+28h]
0x18009d7f4  mov     rsp, r11
0x18009d7f7  pop     rbp
0x18009d7f8  retn
```
