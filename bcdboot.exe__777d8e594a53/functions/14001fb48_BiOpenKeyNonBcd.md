# BiOpenKeyNonBcd

- ea: `0x14001fb48`
- end: `0x14001fc56`
- name: `BiOpenKeyNonBcd`
- size: `270`
- prototype: `__int64 __fastcall(void *, const WCHAR *, ACCESS_MASK, void **)`
- caller_count: `4`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001b354`
- `0x14001bd44`
- `0x14001ed70`
- `0x14001f570`

## callees

- `0x14001fb48`

## import_xrefs

- `ntdll!ZwClose` at `0x14001fc00`
- `ntdll!ZwClose` at `0x14001fc00`
- `ntdll!ZwOpenKey` at `0x14001fbda`
- `ntdll!ZwOpenKey` at `0x14001fbda`
- `ntdll!RtlInitUnicodeString` at `0x14001fb9f`
- `ntdll!RtlInitUnicodeString` at `0x14001fb9f`

## pseudocode

```c
__int64 __fastcall BiOpenKeyNonBcd(void *a1, const WCHAR *a2, ACCESS_MASK a3, void **a4)
{
  unsigned int i; // edi
  NTSTATUS v9; // ebx
  void *KeyHandle; // [rsp+28h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-68h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  for ( i = 0; ; ++i )
  {
    KeyHandle = 0;
    RtlInitUnicodeString(&DestinationString, a2);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = a1;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v9 = ZwOpenKey(&KeyHandle, a3, &ObjectAttributes);
    if ( v9 < 0 )
    {
      if ( KeyHandle )
        ZwClose(KeyHandle);
    }
    else
    {
      *a4 = KeyHandle;
    }
    if ( v9 != -1073741443 )
      break;
    __debugbreak();
    if ( i >= 5 )
      break;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14001fb48  mov     rax, rsp
0x14001fb4b  mov     [rax+20h], r9
0x14001fb4f  mov     [rax+18h], r8d
0x14001fb53  mov     [rax+10h], rdx
0x14001fb57  mov     [rax+8], rcx
0x14001fb5b  push    rbx
0x14001fb5c  push    rsi
0x14001fb5d  push    rdi
0x14001fb5e  push    r12
0x14001fb60  push    r14
0x14001fb62  push    r15
0x14001fb64  sub     rsp, 78h
0x14001fb68  mov     rsi, r9
0x14001fb6b  mov     r14d, r8d
0x14001fb6e  mov     r15, rdx
0x14001fb71  mov     r12, rcx
0x14001fb74  xorps   xmm0, xmm0
0x14001fb77  movups  xmmword ptr [rax-78h], xmm0
0x14001fb7b  xor     eax, eax
0x14001fb7d  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.Length], xmm0
0x14001fb82  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.ObjectName], xmm0
0x14001fb87  movups  xmmword ptr [rsp+0A8h+ObjectAttributes+1Ch], xmm0
0x14001fb8c  xor     edi, edi
0x14001fb8e  mov     [rsp+0A8h+KeyHandle], 0
0x14001fb97  mov     rdx, r15; SourceString
0x14001fb9a  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x14001fb9f  call    cs:__imp_RtlInitUnicodeString
0x14001fba5  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x14001fbad  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], r12
0x14001fbb2  mov     [rsp+0A8h+ObjectAttributes.Attributes], 40h ; '@'
0x14001fbba  lea     rax, [rsp+0A8h+DestinationString]
0x14001fbbf  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rax
0x14001fbc4  xorps   xmm0, xmm0
0x14001fbc7  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001fbcd  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x14001fbd2  mov     edx, r14d; DesiredAccess
0x14001fbd5  lea     rcx, [rsp+0A8h+KeyHandle]; KeyHandle
0x14001fbda  call    cs:__imp_ZwOpenKey
0x14001fbe0  mov     ebx, eax
0x14001fbe2  mov     [rsp+0A8h+var_88], eax
0x14001fbe6  test    eax, eax
0x14001fbe8  js      short loc_14001FBF2
0x14001fbea  mov     rcx, [rsp+0A8h+KeyHandle]
0x14001fbef  mov     [rsi], rcx
0x14001fbf2  test    ebx, ebx
0x14001fbf4  jns     short loc_14001FC06
0x14001fbf6  mov     rcx, [rsp+0A8h+KeyHandle]; Handle
0x14001fbfb  test    rcx, rcx
0x14001fbfe  jz      short loc_14001FC06
0x14001fc00  call    cs:__imp_ZwClose
0x14001fc06  cmp     ebx, 0C000017Dh
0x14001fc0c  jnz     short loc_14001FC46
0x14001fc0e  int     3; Trap to Debugger
0x14001fc0f  jmp     short loc_14001FC3A
0x14001fc11  mov     edi, 5
0x14001fc16  mov     rsi, [rsp+0A8h+arg_18]
0x14001fc1e  mov     r14d, [rsp+0A8h+arg_10]
0x14001fc26  mov     r15, [rsp+0A8h+arg_8]
0x14001fc2e  mov     r12, [rsp+0A8h+arg_0]
0x14001fc36  mov     ebx, [rsp+0A8h+var_88]
0x14001fc3a  cmp     edi, 5
0x14001fc3d  jnb     short loc_14001FC46
0x14001fc3f  inc     edi
0x14001fc41  jmp     loc_14001FB8E
0x14001fc46  mov     eax, ebx
0x14001fc48  add     rsp, 78h
0x14001fc4c  pop     r15
0x14001fc4e  pop     r14
0x14001fc50  pop     r12
0x14001fc52  pop     rdi
0x14001fc53  pop     rsi
0x14001fc54  pop     rbx
0x14001fc55  retn
```
