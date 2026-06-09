# appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::iends_in(wchar_t const *)

- ea: `0x18001a4d4`
- end: `0x18001a58d`
- name: `?iends_in@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEBA_NPEB_W@Z`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018484`
- `0x180019014`

## callees

- `0x18001a4d4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18001a4ee`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001a557`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001a4ee`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001a557`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18001a570`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18001a570`

## pseudocode

```c
bool __fastcall appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::iends_in(
        __int64 a1,
        const WCHAR *a2)
{
  __int64 v3; // r8
  unsigned int v5; // ecx
  __int16 v6; // dx
  __int16 v7; // ax
  __int64 v8; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-28h] BYREF
  UNICODE_STRING String2; // [rsp+30h] [rbp-18h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  v3 = *(unsigned __int16 *)(a1 + 16);
  if ( (unsigned __int16)v3 < DestinationString.Length )
    return 0;
  v5 = *(_DWORD *)a1 >> 1;
  String2 = 0;
  if ( v5 > 0xFFFF )
    v6 = -1;
  else
    v6 = v5;
  v7 = 0;
  if ( v5 <= 0xFFFF )
    v7 = v6;
  v8 = 0;
  if ( v7 )
    v8 = *(_QWORD *)(a1 + 8);
  RtlInitUnicodeString(&String2, (PCWSTR)(v8 + 2 * ((v3 - (unsigned __int64)DestinationString.Length) >> 1)));
  return RtlCompareUnicodeString(&DestinationString, &String2, 1u) == 0;
}

```

## disassembly

```asm
0x18001a4d4  mov     [rsp+arg_0], rbx
0x18001a4d9  push    rdi
0x18001a4da  sub     rsp, 40h
0x18001a4de  mov     rbx, rcx
0x18001a4e1  xorps   xmm0, xmm0
0x18001a4e4  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x18001a4e9  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x18001a4ee  call    cs:__imp_RtlInitUnicodeString
0x18001a4f5  nop     dword ptr [rax+rax+00h]
0x18001a4fa  movzx   r8d, word ptr [rbx+10h]
0x18001a4ff  cmp     r8w, [rsp+48h+DestinationString.Length]
0x18001a505  jnb     short loc_18001A50B
0x18001a507  xor     al, al
0x18001a509  jmp     short loc_18001A581
0x18001a50b  mov     ecx, [rbx]
0x18001a50d  mov     r9d, 0FFFFh
0x18001a513  shr     ecx, 1
0x18001a515  xorps   xmm0, xmm0
0x18001a518  movups  xmmword ptr [rsp+48h+String2.Length], xmm0
0x18001a51d  cmp     ecx, r9d
0x18001a520  ja      short loc_18001A527
0x18001a522  movzx   edx, cx
0x18001a525  jmp     short loc_18001A52A
0x18001a527  mov     edx, r9d
0x18001a52a  xor     edi, edi
0x18001a52c  cmp     ecx, r9d
0x18001a52f  mov     eax, edi
0x18001a531  cmovbe  ax, dx
0x18001a535  mov     edx, edi
0x18001a537  test    ax, ax
0x18001a53a  jz      short loc_18001A540
0x18001a53c  mov     rdx, [rbx+8]
0x18001a540  movzx   eax, [rsp+48h+DestinationString.Length]
0x18001a545  mov     rcx, r8
0x18001a548  sub     rcx, rax
0x18001a54b  shr     rcx, 1
0x18001a54e  lea     rdx, [rdx+rcx*2]; SourceString
0x18001a552  lea     rcx, [rsp+48h+String2]; DestinationString
0x18001a557  call    cs:__imp_RtlInitUnicodeString
0x18001a55e  nop     dword ptr [rax+rax+00h]
0x18001a563  mov     r8b, 1; CaseInSensitive
0x18001a566  lea     rdx, [rsp+48h+String2]; String2
0x18001a56b  lea     rcx, [rsp+48h+DestinationString]; String1
0x18001a570  call    cs:__imp_RtlCompareUnicodeString
0x18001a577  nop     dword ptr [rax+rax+00h]
0x18001a57c  test    eax, eax
0x18001a57e  setz    al
0x18001a581  mov     rbx, [rsp+48h+arg_0]
0x18001a586  add     rsp, 40h
0x18001a58a  pop     rdi
0x18001a58b  retn
```
