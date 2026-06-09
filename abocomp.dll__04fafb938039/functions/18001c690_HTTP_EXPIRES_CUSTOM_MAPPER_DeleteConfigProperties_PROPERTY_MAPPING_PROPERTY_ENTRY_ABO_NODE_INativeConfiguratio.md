# HTTP_EXPIRES_CUSTOM_MAPPER::DeleteConfigProperties(PROPERTY_MAPPING *,PROPERTY_ENTRY *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x18001c690`
- end: `0x18001c759`
- name: `?DeleteConfigProperties@HTTP_EXPIRES_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVPROPERTY_ENTRY@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `201`
- prototype: `__int64 __fastcall(HTTP_EXPIRES_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18001c690`
- `0x18002c010`

## string_xrefs

- `0x18001c71d`: `cacheControlMode`
- `0x18001c6f4`: `cacheControlMaxAge`

## pseudocode

```c
__int64 __fastcall HTTP_EXPIRES_CUSTOM_MAPPER::DeleteConfigProperties(
        HTTP_EXPIRES_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct PROPERTY_ENTRY *a3,
        struct ABO_NODE *a4,
        struct INativeConfigurationElement *a5)
{
  unsigned int v5; // eax
  unsigned int v6; // edx

  if ( a2 && a3 && a4 && a5 )
  {
    v5 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *))(*(_QWORD *)a5 + 184LL))(
           a5,
           L"httpExpires");
    v6 = v5;
    if ( (int)(v5 + 0x80000000) < 0 || v5 == -2147024894 )
    {
      v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *))(*(_QWORD *)a5 + 184LL))(
             a5,
             L"cacheControlMaxAge");
      if ( ((v6 + 0x80000000) & 0x80000000) != 0 || v6 == -2147024894 )
      {
        v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *))(*(_QWORD *)a5 + 184LL))(
               a5,
               L"cacheControlMode");
        if ( ((v6 + 0x80000000) & 0x80000000) != 0 || v6 == -2147024894 )
          return 0;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x18001c690  mov     [rsp+arg_0], rbx
0x18001c695  push    rsi
0x18001c696  sub     rsp, 20h
0x18001c69a  test    rdx, rdx
0x18001c69d  jz      loc_18001C747
0x18001c6a3  test    r8, r8
0x18001c6a6  jz      loc_18001C747
0x18001c6ac  test    r9, r9
0x18001c6af  jz      loc_18001C747
0x18001c6b5  mov     rbx, [rsp+28h+arg_20]
0x18001c6ba  test    rbx, rbx
0x18001c6bd  jz      loc_18001C747
0x18001c6c3  mov     rax, [rbx]
0x18001c6c6  lea     rdx, aHttpexpires; "httpExpires"
0x18001c6cd  mov     rcx, rbx
0x18001c6d0  mov     rax, [rax+0B8h]
0x18001c6d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6dc  mov     esi, 80000000h
0x18001c6e1  mov     edx, eax
0x18001c6e3  lea     ecx, [rax+rsi]
0x18001c6e6  test    esi, ecx
0x18001c6e8  jnz     short loc_18001C6F1
0x18001c6ea  cmp     eax, 80070002h
0x18001c6ef  jnz     short loc_18001C74C
0x18001c6f1  mov     rax, [rbx]
0x18001c6f4  lea     rdx, aCachecontrolma; "cacheControlMaxAge"
0x18001c6fb  mov     rcx, rbx
0x18001c6fe  mov     rax, [rax+0B8h]
0x18001c705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c70a  mov     edx, eax
0x18001c70c  add     eax, esi
0x18001c70e  test    esi, eax
0x18001c710  jnz     short loc_18001C71A
0x18001c712  cmp     edx, 80070002h
0x18001c718  jnz     short loc_18001C74C
0x18001c71a  mov     rax, [rbx]
0x18001c71d  lea     rdx, aCachecontrolmo; "cacheControlMode"
0x18001c724  mov     rcx, rbx
0x18001c727  mov     rax, [rax+0B8h]
0x18001c72e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c733  mov     edx, eax
0x18001c735  add     eax, esi
0x18001c737  test    esi, eax
0x18001c739  jnz     short loc_18001C743
0x18001c73b  cmp     edx, 80070002h
0x18001c741  jnz     short loc_18001C74C
0x18001c743  xor     edx, edx
0x18001c745  jmp     short loc_18001C74C
0x18001c747  mov     edx, 80070057h
0x18001c74c  mov     rbx, [rsp+28h+arg_0]
0x18001c751  mov     eax, edx
0x18001c753  add     rsp, 20h
0x18001c757  pop     rsi
0x18001c758  retn
```
