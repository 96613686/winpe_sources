# Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(void)

- ea: `0x180004764`
- end: `0x1800047fb`
- name: `??0?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@XZ`
- size: `151`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18000e960`
- `0x180011538`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180004788`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800047a2`
- `ntoskrnl!RtlInitUnicodeString` at `0x180004788`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800047a2`

## pseudocode

```c
__int64 __fastcall Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(
        __int64 a1)
{
  __int64 result; // rax

  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  RtlInitUnicodeString((PUNICODE_STRING)(a1 + 32), 0);
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  RtlInitUnicodeString((PUNICODE_STRING)(a1 + 64), 0);
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 136) = a1 + 112;
  *(_QWORD *)(a1 + 128) = a1 + 112;
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 176) = a1 + 152;
  *(_QWORD *)(a1 + 168) = a1 + 152;
  result = a1;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_DWORD *)(a1 + 104) = 0;
  *(_DWORD *)(a1 + 144) = 0;
  return result;
}

```

## disassembly

```asm
0x180004764  mov     [rsp+arg_0], rbx
0x180004769  push    rdi
0x18000476a  sub     rsp, 20h
0x18000476e  xor     edi, edi
0x180004770  mov     rbx, rcx
0x180004773  mov     [rcx], rdi
0x180004776  xor     edx, edx; SourceString
0x180004778  mov     [rcx+8], rdi
0x18000477c  mov     [rcx+10h], rdi
0x180004780  mov     [rcx+18h], rdi
0x180004784  add     rcx, 20h ; ' '; DestinationString
0x180004788  call    cs:__imp_RtlInitUnicodeString
0x18000478f  nop     dword ptr [rax+rax+00h]
0x180004794  lea     rcx, [rbx+40h]; DestinationString
0x180004798  mov     [rbx+30h], rdi
0x18000479c  xor     edx, edx; SourceString
0x18000479e  mov     [rbx+38h], rdi
0x1800047a2  call    cs:__imp_RtlInitUnicodeString
0x1800047a9  nop     dword ptr [rax+rax+00h]
0x1800047ae  lea     rax, [rbx+70h]
0x1800047b2  mov     [rbx+50h], rdi
0x1800047b6  mov     [rax], rdi
0x1800047b9  mov     [rax+8], rdi
0x1800047bd  mov     [rax+18h], rax
0x1800047c1  mov     [rax+10h], rax
0x1800047c5  lea     rax, [rbx+98h]
0x1800047cc  mov     [rax], rdi
0x1800047cf  mov     [rax+8], rdi
0x1800047d3  mov     [rax+18h], rax
0x1800047d7  mov     [rax+10h], rax
0x1800047db  mov     rax, rbx
0x1800047de  mov     [rbx+58h], rdi
0x1800047e2  mov     [rbx+60h], rdi
0x1800047e6  mov     [rbx+68h], edi
0x1800047e9  mov     [rbx+90h], edi
0x1800047ef  mov     rbx, [rsp+28h+arg_0]
0x1800047f4  add     rsp, 20h
0x1800047f8  pop     rdi
0x1800047f9  retn
```
