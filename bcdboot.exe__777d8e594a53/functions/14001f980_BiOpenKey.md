# BiOpenKey

- ea: `0x14001f980`
- end: `0x14001fb41`
- name: `BiOpenKey`
- size: `449`
- prototype: `__int64 __fastcall(unsigned __int64, const WCHAR *, ACCESS_MASK, void **)`
- caller_count: `21`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140013c1c`
- `0x140013ee8`
- `0x140014130`
- `0x140014574`
- `0x140018890`
- `0x140018b54`
- `0x140019990`
- `0x140019bb8`
- `0x14001a964`
- `0x14001af00`
- `0x14001b354`
- `0x14001ba1c`
- `0x14001bd44`
- `0x14001ec14`
- `0x14001ece0`
- `0x14001f324`
- `0x14001fc5c`
- `0x1400201ec`
- `0x1400207d4`
- `0x14002090c`
- `0x140022258`

## callees

- `0x14001e980`
- `0x14001f980`

## import_xrefs

- `ntdll!ZwClose` at `0x14001faa4`
- `ntdll!ZwClose` at `0x14001faca`
- `ntdll!ZwClose` at `0x14001faa4`
- `ntdll!ZwClose` at `0x14001faca`
- `ntdll!ZwSetSecurityObject` at `0x14001fa73`
- `ntdll!ZwSetSecurityObject` at `0x14001fa73`
- `ntdll!ZwOpenKey` at `0x14001fa44`
- `ntdll!ZwOpenKey` at `0x14001fa8f`
- `ntdll!ZwOpenKey` at `0x14001fa44`
- `ntdll!ZwOpenKey` at `0x14001fa8f`
- `ntdll!RtlFreeHeap` at `0x14001fae7`
- `ntdll!RtlFreeHeap` at `0x14001fae7`
- `ntdll!RtlInitUnicodeString` at `0x14001f9e0`
- `ntdll!RtlInitUnicodeString` at `0x14001f9e0`

## pseudocode

```c
__int64 __fastcall BiOpenKey(unsigned __int64 a1, const WCHAR *a2, ACCESS_MASK a3, void **a4)
{
  unsigned int i; // edi
  struct _ACL *KeySecurityDescriptor; // r14
  ACCESS_MASK v10; // edx
  NTSTATUS v11; // ebx
  void *KeyHandle; // [rsp+28h] [rbp-90h] BYREF
  void *v14; // [rsp+30h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-70h] BYREF
  unsigned __int64 v17; // [rsp+C0h] [rbp+8h]

  v14 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  for ( i = 0; ; ++i )
  {
    KeyHandle = 0;
    KeySecurityDescriptor = 0;
    RtlInitUnicodeString(&DestinationString, a2);
    v17 = a1 & 0xFFFFFFFFFFFFFFFDuLL;
    a3 |= 0x40000u;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = (HANDLE)(a1 & 0xFFFFFFFFFFFFFFFDuLL);
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v10 = 0x40000;
    if ( (a3 & 0x60019) == a3 )
      v10 = a3;
    v11 = ZwOpenKey(&KeyHandle, v10, &ObjectAttributes);
    if ( v11 >= 0 )
    {
      if ( (a3 & 0x60019) == a3 )
        goto LABEL_9;
      KeySecurityDescriptor = BiCreateKeySecurityDescriptor(0xF003Fu);
      v11 = ZwSetSecurityObject(KeyHandle, 4u, KeySecurityDescriptor);
      if ( v11 >= 0 )
      {
        v11 = ZwOpenKey(&v14, a3, &ObjectAttributes);
        if ( v11 >= 0 )
        {
          ZwClose(KeyHandle);
          KeyHandle = v14;
LABEL_9:
          *a4 = KeyHandle;
        }
      }
    }
    if ( v11 < 0 && KeyHandle )
      ZwClose(KeyHandle);
    if ( KeySecurityDescriptor )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, KeySecurityDescriptor);
    if ( v11 != -1073741443 )
      break;
    __debugbreak();
    if ( i >= 5 )
      break;
    a1 = v17;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14001f980  mov     [rsp+arg_18], r9
0x14001f985  mov     [rsp+arg_8], rdx
0x14001f98a  push    rbx
0x14001f98b  push    rsi
0x14001f98c  push    rdi
0x14001f98d  push    r12
0x14001f98f  push    r13
0x14001f991  push    r14
0x14001f993  push    r15
0x14001f995  sub     rsp, 80h
0x14001f99c  mov     r15, r9
0x14001f99f  mov     esi, r8d
0x14001f9a2  mov     r13, rdx
0x14001f9a5  mov     rbx, rcx
0x14001f9a8  mov     [rsp+0B8h+var_88], 0
0x14001f9b1  xorps   xmm0, xmm0
0x14001f9b4  movups  xmmword ptr [rsp+0B8h+DestinationString.Length], xmm0
0x14001f9b9  xor     eax, eax
0x14001f9bb  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.Length], xmm0
0x14001f9c0  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.ObjectName], xmm0
0x14001f9c5  movups  xmmword ptr [rsp+0B8h+ObjectAttributes+1Ch], xmm0
0x14001f9ca  xor     edi, edi
0x14001f9cc  mov     [rsp+0B8h+KeyHandle], 0
0x14001f9d5  xor     r14d, r14d
0x14001f9d8  mov     rdx, r13; SourceString
0x14001f9db  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x14001f9e0  call    cs:__imp_RtlInitUnicodeString
0x14001f9e6  and     rbx, 0FFFFFFFFFFFFFFFDh
0x14001f9ea  mov     [rsp+0B8h+arg_0], rbx
0x14001f9f2  bts     esi, 12h
0x14001f9f6  mov     [rsp+0B8h+arg_10], esi
0x14001f9fd  mov     r12d, esi
0x14001fa00  and     r12d, 60019h
0x14001fa07  mov     [rsp+0B8h+ObjectAttributes.Length], 30h ; '0'
0x14001fa0f  mov     [rsp+0B8h+ObjectAttributes.RootDirectory], rbx
0x14001fa14  mov     [rsp+0B8h+ObjectAttributes.Attributes], 40h ; '@'
0x14001fa1c  lea     rax, [rsp+0B8h+DestinationString]
0x14001fa21  mov     [rsp+0B8h+ObjectAttributes.ObjectName], rax
0x14001fa26  xorps   xmm0, xmm0
0x14001fa29  movdqu  xmmword ptr [rsp+0B8h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001fa2f  mov     edx, 40000h
0x14001fa34  cmp     r12d, esi
0x14001fa37  cmovz   edx, esi; DesiredAccess
0x14001fa3a  lea     r8, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x14001fa3f  lea     rcx, [rsp+0B8h+KeyHandle]; KeyHandle
0x14001fa44  call    cs:__imp_ZwOpenKey
0x14001fa4a  mov     ebx, eax
0x14001fa4c  mov     [rsp+0B8h+var_98], eax
0x14001fa50  test    eax, eax
0x14001fa52  js      short loc_14001FABC
0x14001fa54  cmp     r12d, esi
0x14001fa57  jz      short loc_14001FAB4
0x14001fa59  mov     ecx, 0F003Fh; AccessMask
0x14001fa5e  call    BiCreateKeySecurityDescriptor
0x14001fa63  mov     r14, rax
0x14001fa66  mov     r8, rax; SecurityDescriptor
0x14001fa69  mov     edx, 4; SecurityInformation
0x14001fa6e  mov     rcx, [rsp+0B8h+KeyHandle]; Handle
0x14001fa73  call    cs:__imp_ZwSetSecurityObject
0x14001fa79  mov     ebx, eax
0x14001fa7b  mov     [rsp+0B8h+var_98], eax
0x14001fa7f  test    eax, eax
0x14001fa81  js      short loc_14001FABC
0x14001fa83  lea     r8, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x14001fa88  mov     edx, esi; DesiredAccess
0x14001fa8a  lea     rcx, [rsp+0B8h+var_88]; KeyHandle
0x14001fa8f  call    cs:__imp_ZwOpenKey
0x14001fa95  mov     ebx, eax
0x14001fa97  mov     [rsp+0B8h+var_98], eax
0x14001fa9b  test    eax, eax
0x14001fa9d  js      short loc_14001FABC
0x14001fa9f  mov     rcx, [rsp+0B8h+KeyHandle]; Handle
0x14001faa4  call    cs:__imp_ZwClose
0x14001faaa  mov     rax, [rsp+0B8h+var_88]
0x14001faaf  mov     [rsp+0B8h+KeyHandle], rax
0x14001fab4  mov     rax, [rsp+0B8h+KeyHandle]
0x14001fab9  mov     [r15], rax
0x14001fabc  test    ebx, ebx
0x14001fabe  jns     short loc_14001FAD0
0x14001fac0  mov     rcx, [rsp+0B8h+KeyHandle]; Handle
0x14001fac5  test    rcx, rcx
0x14001fac8  jz      short loc_14001FAD0
0x14001faca  call    cs:__imp_ZwClose
0x14001fad0  test    r14, r14
0x14001fad3  jz      short loc_14001FAED
0x14001fad5  mov     rcx, gs:60h
0x14001fade  mov     r8, r14; P
0x14001fae1  xor     edx, edx; Flags
0x14001fae3  mov     rcx, [rcx+30h]; HeapHandle
0x14001fae7  call    cs:__imp_RtlFreeHeap
0x14001faed  cmp     ebx, 0C000017Dh
0x14001faf3  jnz     short loc_14001FB2C
0x14001faf5  int     3; Trap to Debugger
0x14001faf6  jmp     short loc_14001FB18
0x14001faf8  mov     edi, 5
0x14001fafd  mov     r15, [rsp+0B8h+arg_18]
0x14001fb05  mov     esi, [rsp+0B8h+arg_10]
0x14001fb0c  mov     r13, [rsp+0B8h+arg_8]
0x14001fb14  mov     ebx, [rsp+0B8h+var_98]
0x14001fb18  cmp     edi, 5
0x14001fb1b  jnb     short loc_14001FB2C
0x14001fb1d  inc     edi
0x14001fb1f  mov     rbx, [rsp+0B8h+arg_0]
0x14001fb27  jmp     loc_14001F9CC
0x14001fb2c  mov     eax, ebx
0x14001fb2e  add     rsp, 80h
0x14001fb35  pop     r15
0x14001fb37  pop     r14
0x14001fb39  pop     r13
0x14001fb3b  pop     r12
0x14001fb3d  pop     rdi
0x14001fb3e  pop     rsi
0x14001fb3f  pop     rbx
0x14001fb40  retn
```
