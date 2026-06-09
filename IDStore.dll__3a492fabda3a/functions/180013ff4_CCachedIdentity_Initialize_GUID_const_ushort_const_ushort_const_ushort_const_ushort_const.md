# CCachedIdentity::Initialize(_GUID const &,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180013ff4`
- end: `0x1800140e2`
- name: `?Initialize@CCachedIdentity@@QEAAJAEBU_GUID@@PEBG111@Z`
- size: `238`
- prototype: `__int64 __fastcall(struct _GUID *this, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008260`

## callees

- `0x18000a680`
- `0x180013ff4`
- `0x180019750`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001405e`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001405e`

## string_xrefs

- `0x18001404e`: `IDStoreCache`
- `0x180014024`: `Software\Microsoft\IdentityStore\Cache`

## pseudocode

```c
__int64 __fastcall CCachedIdentity::Initialize(
        struct _GUID *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6)
{
  int PersistedRegistryLocationW; // eax
  const unsigned __int16 *v10; // rdx
  __int64 result; // rax
  _BYTE v12[528]; // [rsp+30h] [rbp-248h] BYREF

  *this = *a2;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"IDStoreCache",
                                 L"Software\\Microsoft\\IdentityStore\\Cache",
                                 v12,
                                 520,
                                 0);
  v10 = (const unsigned __int16 *)v12;
  if ( PersistedRegistryLocationW )
    v10 = L"Software\\Microsoft\\IdentityStore\\Cache";
  result = CDynamicString::Assign((CDynamicString *)&this[9], v10);
  if ( (int)result >= 0 )
  {
    result = CDynamicString::Assign((CDynamicString *)&this[1], a3);
    if ( (int)result >= 0 )
    {
      result = CDynamicString::Assign((CDynamicString *)&this[3], a4);
      if ( (int)result >= 0 )
      {
        result = CDynamicString::Assign((CDynamicString *)&this[5], a5);
        if ( (int)result >= 0 )
          return CDynamicString::Assign((CDynamicString *)&this[7], a6);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180013ff4  mov     [rsp+arg_8], rbx
0x180013ff9  push    rbp
0x180013ffa  push    rsi
0x180013ffb  push    rdi
0x180013ffc  push    r14
0x180013ffe  push    r15
0x180014000  sub     rsp, 250h
0x180014007  mov     rax, cs:__security_cookie
0x18001400e  xor     rax, rsp
0x180014011  mov     [rsp+278h+var_38], rax
0x180014019  movups  xmm0, xmmword ptr [rdx]
0x18001401c  mov     r14, [rsp+278h+arg_20]
0x180014024  lea     r15, aSoftwareMicros; "Software\\Microsoft\\IdentityStore\\Cac"...
0x18001402b  mov     rdi, [rsp+278h+arg_28]
0x180014033  mov     rbp, r9
0x180014036  movdqu  xmmword ptr [rcx], xmm0
0x18001403a  mov     rsi, r8
0x18001403d  mov     [rsp+278h+var_258], 0
0x180014046  mov     rbx, rcx
0x180014049  lea     r8, [rsp+278h+var_248]
0x18001404e  lea     rcx, aIdstorecache; "IDStoreCache"
0x180014055  mov     r9d, 208h
0x18001405b  mov     rdx, r15
0x18001405e  call    cs:__imp_GetPersistedRegistryLocationW
0x180014064  test    eax, eax
0x180014066  lea     rdx, [rsp+278h+var_248]
0x18001406b  lea     rcx, [rbx+90h]; this
0x180014072  cmovnz  rdx, r15; unsigned __int16 *
0x180014076  call    ?Assign@CDynamicString@@QEAAJPEBG@Z; CDynamicString::Assign(ushort const *)
0x18001407b  test    eax, eax
0x18001407d  js      short loc_1800140BB
0x18001407f  lea     rcx, [rbx+10h]; this
0x180014083  mov     rdx, rsi; unsigned __int16 *
0x180014086  call    ?Assign@CDynamicString@@QEAAJPEBG@Z; CDynamicString::Assign(ushort const *)
0x18001408b  test    eax, eax
0x18001408d  js      short loc_1800140BB
0x18001408f  lea     rcx, [rbx+30h]; this
0x180014093  mov     rdx, rbp; unsigned __int16 *
0x180014096  call    ?Assign@CDynamicString@@QEAAJPEBG@Z; CDynamicString::Assign(ushort const *)
0x18001409b  test    eax, eax
0x18001409d  js      short loc_1800140BB
0x18001409f  lea     rcx, [rbx+50h]; this
0x1800140a3  mov     rdx, r14; unsigned __int16 *
0x1800140a6  call    ?Assign@CDynamicString@@QEAAJPEBG@Z; CDynamicString::Assign(ushort const *)
0x1800140ab  test    eax, eax
0x1800140ad  js      short loc_1800140BB
0x1800140af  lea     rcx, [rbx+70h]; this
0x1800140b3  mov     rdx, rdi; unsigned __int16 *
0x1800140b6  call    ?Assign@CDynamicString@@QEAAJPEBG@Z; CDynamicString::Assign(ushort const *)
0x1800140bb  mov     rcx, [rsp+278h+var_38]
0x1800140c3  xor     rcx, rsp; StackCookie
0x1800140c6  call    __security_check_cookie
0x1800140cb  mov     rbx, [rsp+278h+arg_8]
0x1800140d3  add     rsp, 250h
0x1800140da  pop     r15
0x1800140dc  pop     r14
0x1800140de  pop     rdi
0x1800140df  pop     rsi
0x1800140e0  pop     rbp
0x1800140e1  retn
```
