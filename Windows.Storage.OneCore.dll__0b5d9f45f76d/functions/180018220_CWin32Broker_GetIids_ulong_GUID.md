# CWin32Broker::GetIids(ulong *,_GUID * *)

- ea: `0x180018220`
- end: `0x18001828d`
- name: `?GetIids@CWin32Broker@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(CWin32Broker *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180018220`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018242`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018242`

## pseudocode

```c
__int64 __fastcall CWin32Broker::GetIids(CWin32Broker *this, unsigned int *a2, struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_684a703a_2827_4459_9944_644fb342097b;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_e5305f56_8174_43c2_a911_fdb7972e8709;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180018220  mov     [rsp+arg_0], rbx
0x180018225  push    rdi
0x180018226  sub     rsp, 20h
0x18001822a  mov     qword ptr [r8], 0
0x180018231  mov     ecx, 30h ; '0'; cb
0x180018236  mov     dword ptr [rdx], 0
0x18001823c  mov     rbx, r8
0x18001823f  mov     rdi, rdx
0x180018242  call    cs:__imp_CoTaskMemAlloc
0x180018248  test    rax, rax
0x18001824b  jnz     short loc_180018254
0x18001824d  mov     eax, 8007000Eh
0x180018252  jmp     short loc_180018282
0x180018254  movups  xmm0, xmmword ptr cs:_GUID_684a703a_2827_4459_9944_644fb342097b.Data1
0x18001825b  movdqu  xmmword ptr [rax], xmm0
0x18001825f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180018266  movdqu  xmmword ptr [rax+10h], xmm1
0x18001826b  movups  xmm0, xmmword ptr cs:_GUID_e5305f56_8174_43c2_a911_fdb7972e8709.Data1
0x180018272  movdqu  xmmword ptr [rax+20h], xmm0
0x180018277  mov     dword ptr [rdi], 3
0x18001827d  mov     [rbx], rax
0x180018280  xor     eax, eax
0x180018282  mov     rbx, [rsp+28h+arg_0]
0x180018287  add     rsp, 20h
0x18001828b  pop     rdi
0x18001828c  retn
```
