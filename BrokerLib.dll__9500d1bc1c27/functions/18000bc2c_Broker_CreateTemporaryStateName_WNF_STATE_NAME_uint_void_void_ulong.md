# Broker::CreateTemporaryStateName(_WNF_STATE_NAME *,uint,void *,void *,ulong)

- ea: `0x18000bc2c`
- end: `0x18000bcb5`
- name: `?CreateTemporaryStateName@Broker@@YAJPEAU_WNF_STATE_NAME@@IPEAX1K@Z`
- size: `137`
- prototype: `int(Broker *__hidden this, struct _WNF_STATE_NAME *, unsigned int, void *, void *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180017a9c`
- `0x1800192fc`

## callees

- `0x18000bc2c`
- `0x18000bcc0`

## import_xrefs

- `ntdll!NtCreateWnfStateName` at `0x18000bc85`
- `ntdll!NtCreateWnfStateName` at `0x18000bc85`
- `ntdll!RtlFreeHeap` at `0x18000bca4`
- `ntdll!RtlFreeHeap` at `0x18000bca4`

## pseudocode

```c
__int64 __fastcall Broker::CreateTemporaryStateName(Broker *this, struct _WNF_STATE_NAME *a2, void *a3, void *a4)
{
  int v5; // eax
  PVOID v6; // rbx
  unsigned int WnfStateName; // edi
  PVOID P; // [rsp+88h] [rbp+20h] BYREF

  P = 0;
  v5 = Broker::CreateStateSecurityDescriptor(a3, a2, (__int64)a3, a4, &P);
  v6 = P;
  WnfStateName = v5;
  if ( v5 >= 0 )
    WnfStateName = NtCreateWnfStateName(this, 3, 0);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  return WnfStateName;
}

```

## disassembly

```asm
0x18000bc2c  mov     r11, rsp
0x18000bc2f  mov     [r11+20h], r9
0x18000bc33  push    rbx
0x18000bc34  push    rbp
0x18000bc35  push    rsi
0x18000bc36  push    rdi
0x18000bc37  sub     rsp, 48h
0x18000bc3b  mov     rbp, rcx
0x18000bc3e  mov     qword ptr [r11+20h], 0
0x18000bc46  lea     rax, [r11+20h]
0x18000bc4a  mov     rcx, r8; Owner
0x18000bc4d  mov     [r11-48h], rax
0x18000bc51  mov     esi, edx
0x18000bc53  call    ?CreateStateSecurityDescriptor@Broker@@YAJPEAXK0KPEAPEAX@Z; Broker::CreateStateSecurityDescriptor(void *,ulong,void *,ulong,void * *)
0x18000bc58  mov     rbx, [rsp+68h+P]
0x18000bc60  mov     edi, eax
0x18000bc62  test    eax, eax
0x18000bc64  js      short loc_18000BC8D
0x18000bc66  xor     r9d, r9d
0x18000bc69  mov     [rsp+68h+var_38], rbx
0x18000bc6e  mov     [rsp+68h+var_40], esi
0x18000bc72  xor     r8d, r8d
0x18000bc75  mov     rcx, rbp
0x18000bc78  mov     [rsp+68h+var_48], 0
0x18000bc81  lea     edx, [r9+3]
0x18000bc85  call    cs:__imp_NtCreateWnfStateName
0x18000bc8b  mov     edi, eax
0x18000bc8d  test    rbx, rbx
0x18000bc90  jz      short loc_18000BCAA
0x18000bc92  mov     rcx, gs:60h
0x18000bc9b  mov     r8, rbx; P
0x18000bc9e  xor     edx, edx; Flags
0x18000bca0  mov     rcx, [rcx+30h]; HeapHandle
0x18000bca4  call    cs:__imp_RtlFreeHeap
0x18000bcaa  mov     eax, edi
0x18000bcac  add     rsp, 48h
0x18000bcb0  pop     rdi
0x18000bcb1  pop     rsi
0x18000bcb2  pop     rbp
0x18000bcb3  pop     rbx
0x18000bcb4  retn
```
