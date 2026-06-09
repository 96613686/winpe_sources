# IP_SECURITY_CUSTOM_MAPPER::SetConfigProperties(PROPERTY_MAPPING *,PROPERTY_ENTRY *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x1800239e0`
- end: `0x180023b59`
- name: `?SetConfigProperties@IP_SECURITY_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVPROPERTY_ENTRY@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `377`
- prototype: `__int64 __fastcall(IP_SECURITY_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002990`
- `0x18001bd20`
- `0x18001d2e8`
- `0x1800239e0`
- `0x18002c010`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180023a28`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180023a84`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180023a90`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180023a28`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180023a84`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180023a90`

## pseudocode

```c
__int64 __fastcall IP_SECURITY_CUSTOM_MAPPER::SetConfigProperties(
        IP_SECURITY_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct PROPERTY_ENTRY *a3,
        struct ABO_NODE *a4,
        struct INativeConfigurationElement *a5)
{
  struct INativeConfigurationElementCollection *v5; // rcx
  struct INativeConfigurationElement *v6; // rdi
  BUFFER *v7; // rsi
  int v8; // ebx
  char *v9; // rax
  char *v10; // rdi
  int v11; // ebx
  IP_SECURITY_CUSTOM_MAPPER *v12; // rcx
  unsigned int v13; // edx
  IP_SECURITY_CUSTOM_MAPPER *v14; // rcx
  IP_SECURITY_CUSTOM_MAPPER *v15; // rcx
  IP_SECURITY_CUSTOM_MAPPER *v16; // rcx
  struct INativeConfigurationElementCollection *v18; // [rsp+48h] [rbp+10h] BYREF

  v5 = 0;
  v18 = 0;
  if ( a2 && a3 && a4 && (v6 = a5) != 0 )
  {
    v7 = (struct PROPERTY_ENTRY *)((char *)a3 + 16);
    v8 = 0;
    if ( *((_DWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a3 + 16)) + 4) )
    {
      v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, struct INativeConfigurationElementCollection **))(*(_QWORD *)v6 + 40LL))(
             v6,
             &v18);
      if ( v8 >= 0 )
      {
        v9 = (char *)operator new(0x28u);
        v10 = v9;
        if ( v9 )
        {
          *(_QWORD *)(v9 + 12) = 0;
          *(_QWORD *)v9 = 0;
          *((_DWORD *)v9 + 2) = 0;
          v11 = *((_DWORD *)BUFFER::QueryPtr(v7) + 4);
          v12 = (IP_SECURITY_CUSTOM_MAPPER *)*((_QWORD *)BUFFER::QueryPtr(v7) + 3);
          *(_QWORD *)v10 = v12;
          *((_DWORD *)v10 + 4) = 0;
          *((_DWORD *)v10 + 3) = v11;
          *((_DWORD *)v10 + 2) = v11;
          v8 = IP_SECURITY_CUSTOM_MAPPER::SerializeAddress(v12, (unsigned int **)v10, v18, 0, 1);
          if ( v8 >= 0 )
          {
            v8 = IP_SECURITY_CUSTOM_MAPPER::SerializeAddress(v14, (unsigned int **)v10, v18, 1u, 1);
            if ( v8 >= 0 )
            {
              v8 = IP_SECURITY_CUSTOM_MAPPER::SerializeAddress(v15, (unsigned int **)v10, v18, 0, 0);
              if ( v8 >= 0 )
                v8 = IP_SECURITY_CUSTOM_MAPPER::SerializeAddress(v16, (unsigned int **)v10, v18, 1u, 0);
            }
          }
          ADDRESS_CHECK::`scalar deleting destructor'((ADDRESS_CHECK *)v10, v13);
        }
        else
        {
          v8 = -2147024888;
        }
      }
    }
    v5 = v18;
  }
  else
  {
    v8 = -2147024809;
  }
  if ( v5 )
    (*(void (__fastcall **)(struct INativeConfigurationElementCollection *))(*(_QWORD *)v5 + 16LL))(v5);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800239e0  mov     [rsp+arg_0], rbx
0x1800239e5  mov     [rsp+arg_10], rsi
0x1800239ea  push    rdi
0x1800239eb  sub     rsp, 30h
0x1800239ef  xor     ecx, ecx
0x1800239f1  mov     [rsp+38h+arg_8], rcx
0x1800239f6  test    rdx, rdx
0x1800239f9  jz      loc_180023B31
0x1800239ff  test    r8, r8
0x180023a02  jz      loc_180023B31
0x180023a08  test    r9, r9
0x180023a0b  jz      loc_180023B31
0x180023a11  mov     rdi, [rsp+38h+arg_20]
0x180023a16  test    rdi, rdi
0x180023a19  jz      loc_180023B31
0x180023a1f  lea     rsi, [r8+10h]
0x180023a23  xor     ebx, ebx
0x180023a25  mov     rcx, rsi
0x180023a28  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180023a2e  cmp     [rax+10h], ebx
0x180023a31  jz      loc_180023B2A
0x180023a37  mov     rax, [rdi]
0x180023a3a  lea     rdx, [rsp+38h+arg_8]
0x180023a3f  mov     rcx, rdi
0x180023a42  mov     rax, [rax+28h]
0x180023a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a4b  mov     ebx, eax
0x180023a4d  test    eax, eax
0x180023a4f  js      loc_180023B2A
0x180023a55  mov     ecx, 28h ; '('; Size
0x180023a5a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023a5f  mov     rdi, rax
0x180023a62  test    rax, rax
0x180023a65  jz      loc_180023B25
0x180023a6b  mov     rcx, rsi
0x180023a6e  mov     qword ptr [rax+0Ch], 0
0x180023a76  mov     qword ptr [rax], 0
0x180023a7d  mov     dword ptr [rax+8], 0
0x180023a84  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180023a8a  mov     rcx, rsi
0x180023a8d  mov     ebx, [rax+10h]
0x180023a90  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180023a96  mov     esi, 1
0x180023a9b  xor     r9d, r9d; int
0x180023a9e  mov     rdx, rdi; struct ADDRESS_CHECK *
0x180023aa1  mov     [rsp+38h+var_18], esi; int
0x180023aa5  mov     rcx, [rax+18h]; this
0x180023aa9  mov     [rdi], rcx
0x180023aac  mov     dword ptr [rdi+10h], 0
0x180023ab3  mov     [rdi+0Ch], ebx
0x180023ab6  mov     [rdi+8], ebx
0x180023ab9  mov     r8, [rsp+38h+arg_8]; struct INativeConfigurationElementCollection *
0x180023abe  call    ?SerializeAddress@IP_SECURITY_CUSTOM_MAPPER@@QEAAJPEAVADDRESS_CHECK@@PEAVINativeConfigurationElementCollection@@HH@Z; IP_SECURITY_CUSTOM_MAPPER::SerializeAddress(ADDRESS_CHECK *,INativeConfigurationElementCollection *,int,int)
0x180023ac3  mov     ebx, eax
0x180023ac5  test    eax, eax
0x180023ac7  js      short loc_180023B1B
0x180023ac9  mov     r8, [rsp+38h+arg_8]; struct INativeConfigurationElementCollection *
0x180023ace  mov     r9d, esi; int
0x180023ad1  mov     rdx, rdi; struct ADDRESS_CHECK *
0x180023ad4  mov     [rsp+38h+var_18], esi; int
0x180023ad8  call    ?SerializeAddress@IP_SECURITY_CUSTOM_MAPPER@@QEAAJPEAVADDRESS_CHECK@@PEAVINativeConfigurationElementCollection@@HH@Z; IP_SECURITY_CUSTOM_MAPPER::SerializeAddress(ADDRESS_CHECK *,INativeConfigurationElementCollection *,int,int)
0x180023add  mov     ebx, eax
0x180023adf  test    eax, eax
0x180023ae1  js      short loc_180023B1B
0x180023ae3  mov     r8, [rsp+38h+arg_8]; struct INativeConfigurationElementCollection *
0x180023ae8  xor     r9d, r9d; int
0x180023aeb  mov     rdx, rdi; struct ADDRESS_CHECK *
0x180023aee  mov     [rsp+38h+var_18], 0; int
0x180023af6  call    ?SerializeAddress@IP_SECURITY_CUSTOM_MAPPER@@QEAAJPEAVADDRESS_CHECK@@PEAVINativeConfigurationElementCollection@@HH@Z; IP_SECURITY_CUSTOM_MAPPER::SerializeAddress(ADDRESS_CHECK *,INativeConfigurationElementCollection *,int,int)
0x180023afb  mov     ebx, eax
0x180023afd  test    eax, eax
0x180023aff  js      short loc_180023B1B
0x180023b01  mov     r8, [rsp+38h+arg_8]; struct INativeConfigurationElementCollection *
0x180023b06  mov     r9d, esi; int
0x180023b09  mov     rdx, rdi; struct ADDRESS_CHECK *
0x180023b0c  mov     [rsp+38h+var_18], 0; int
0x180023b14  call    ?SerializeAddress@IP_SECURITY_CUSTOM_MAPPER@@QEAAJPEAVADDRESS_CHECK@@PEAVINativeConfigurationElementCollection@@HH@Z; IP_SECURITY_CUSTOM_MAPPER::SerializeAddress(ADDRESS_CHECK *,INativeConfigurationElementCollection *,int,int)
0x180023b19  mov     ebx, eax
0x180023b1b  mov     rcx, rdi; this
0x180023b1e  call    ??_GADDRESS_CHECK@@QEAAPEAXI@Z; ADDRESS_CHECK::`scalar deleting destructor'(uint)
0x180023b23  jmp     short loc_180023B2A
0x180023b25  mov     ebx, 80070008h
0x180023b2a  mov     rcx, [rsp+38h+arg_8]
0x180023b2f  jmp     short loc_180023B36
0x180023b31  mov     ebx, 80070057h
0x180023b36  test    rcx, rcx
0x180023b39  jz      short loc_180023B47
0x180023b3b  mov     rax, [rcx]
0x180023b3e  mov     rax, [rax+10h]
0x180023b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b47  mov     rsi, [rsp+38h+arg_10]
0x180023b4c  mov     eax, ebx
0x180023b4e  mov     rbx, [rsp+38h+arg_0]
0x180023b53  add     rsp, 30h
0x180023b57  pop     rdi
0x180023b58  retn
```
