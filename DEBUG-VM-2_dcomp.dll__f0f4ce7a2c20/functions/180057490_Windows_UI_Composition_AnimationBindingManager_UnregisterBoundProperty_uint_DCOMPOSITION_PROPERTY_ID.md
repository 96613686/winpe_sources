# Windows::UI::Composition::AnimationBindingManager::UnregisterBoundProperty(uint,DCOMPOSITION_PROPERTY_ID)

- ea: `0x180057490`
- end: `0x180057530`
- name: `?UnregisterBoundProperty@AnimationBindingManager@Composition@UI@Windows@@AEAAXIUDCOMPOSITION_PROPERTY_ID@@@Z`
- size: `160`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180032ff0`
- `0x1800571f4`

## callees

- `0x180057490`
- `0x1800f6f34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180057528`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180057528`
- `ntdll!RtlDeleteElementGenericTable` at `0x180057504`
- `ntdll!RtlDeleteElementGenericTable` at `0x180057504`
- `ntdll!RtlLookupElementGenericTable` at `0x1800574b6`
- `ntdll!RtlLookupElementGenericTable` at `0x1800574b6`

## pseudocode

```c
void __fastcall Windows::UI::Composition::AnimationBindingManager::UnregisterBoundProperty(
        struct _RTL_GENERIC_TABLE *a1,
        int a2,
        int a3)
{
  struct _RTL_GENERIC_TABLE *v3; // rsi
  _QWORD *v5; // r14
  _DWORD *v6; // rcx
  _QWORD *v7; // rdx
  _QWORD *v8; // rax
  int Buffer; // [rsp+20h] [rbp-48h] BYREF
  __int64 v10; // [rsp+28h] [rbp-40h]
  int v11; // [rsp+30h] [rbp-38h] BYREF
  __int64 v12; // [rsp+38h] [rbp-30h]

  v3 = a1 + 1;
  Buffer = a2;
  v10 = 0;
  v5 = RtlLookupElementGenericTable(a1 + 1, &Buffer);
  v6 = (_DWORD *)v5[1];
  v7 = v5 + 1;
  while ( v6 )
  {
    v8 = v6 + 2;
    if ( *v6 == a3 )
    {
      *v7 = *v8;
      operator delete(v6, 0x10u);
      break;
    }
    v6 = (_DWORD *)*v8;
    v7 = v8;
  }
  if ( !v5[1] )
  {
    v11 = *(_DWORD *)v5;
    v12 = 0;
    if ( !RtlDeleteElementGenericTable(v3, &v11) )
      RaiseFailFastException(0, 0, 1u);
  }
}

```

## disassembly

```asm
0x180057490  push    rbx
0x180057492  push    rsi
0x180057493  push    rdi
0x180057494  push    r14
0x180057496  sub     rsp, 48h
0x18005749a  lea     rsi, [rcx+48h]
0x18005749e  mov     [rsp+68h+Buffer], edx
0x1800574a2  mov     rcx, rsi; Table
0x1800574a5  mov     [rsp+68h+var_40], 0
0x1800574ae  lea     rdx, [rsp+68h+Buffer]; Buffer
0x1800574b3  mov     ebx, r8d
0x1800574b6  call    cs:__imp_RtlLookupElementGenericTable
0x1800574bc  mov     r14, rax
0x1800574bf  lea     rdi, [rax+8]
0x1800574c3  mov     rcx, [rdi]; void *
0x1800574c6  mov     rdx, rdi
0x1800574c9  test    rcx, rcx
0x1800574cc  jz      short loc_1800574E6
0x1800574ce  lea     rax, [rcx+8]
0x1800574d2  cmp     [rcx], ebx
0x1800574d4  jnz     short loc_180057518
0x1800574d6  mov     rax, [rax]
0x1800574d9  mov     [rdx], rax
0x1800574dc  mov     edx, 10h; unsigned __int64
0x1800574e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800574e6  cmp     qword ptr [rdi], 0
0x1800574ea  jnz     short loc_18005750E
0x1800574ec  mov     eax, [r14]
0x1800574ef  lea     rdx, [rsp+68h+var_38]; Buffer
0x1800574f4  mov     rcx, rsi; Table
0x1800574f7  mov     [rsp+68h+var_38], eax
0x1800574fb  mov     [rsp+68h+var_30], 0
0x180057504  call    cs:__imp_RtlDeleteElementGenericTable
0x18005750a  test    al, al
0x18005750c  jz      short loc_180057520
0x18005750e  add     rsp, 48h
0x180057512  pop     r14
0x180057514  pop     rdi
0x180057515  pop     rsi
0x180057516  pop     rbx
0x180057517  retn
0x180057518  mov     rcx, [rax]
0x18005751b  mov     rdx, rax
0x18005751e  jmp     short loc_1800574C9
0x180057520  xor     edx, edx; pContextRecord
0x180057522  xor     ecx, ecx; pExceptionRecord
0x180057524  lea     r8d, [rdx+1]; dwFlags
0x180057528  call    cs:__imp_RaiseFailFastException
0x18005752e  jmp     short loc_18005750E
```
