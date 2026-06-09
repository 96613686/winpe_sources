# Windows::Networking::UX::Internal::WlanNetwork::MoveDataIn(Windows::Networking::UX::Internal::WlanNetworkData *)

- ea: `0x180059580`
- end: `0x1800596ee`
- name: `?MoveDataIn@WlanNetwork@Internal@UX@Networking@Windows@@UEAAJPEAUWlanNetworkData@2345@@Z`
- size: `366`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::WlanNetwork *__hidden this, struct Windows::Networking::UX::Internal::WlanNetworkData *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180059ee0`

## callees

- `0x18002f290`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059594`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800595b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059594`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800595b6`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::WlanNetwork::MoveDataIn(
        Windows::Networking::UX::Internal::WlanNetwork *this,
        struct Windows::Networking::UX::Internal::WlanNetworkData *a2)
{
  int v4; // eax
  __int64 result; // rax

  WindowsDeleteString(*((HSTRING *)this - 6));
  *((_QWORD *)this - 6) = 0;
  *((_QWORD *)this - 6) = *((_QWORD *)a2 + 4);
  *((_QWORD *)a2 + 4) = 0;
  WindowsDeleteString(*((HSTRING *)this - 3));
  *((_QWORD *)this - 3) = 0;
  *((_QWORD *)this - 3) = *((_QWORD *)a2 + 7);
  *((_QWORD *)a2 + 7) = 0;
  wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
    (char *)this + 152,
    (char *)a2 + 200);
  *(_OWORD *)((char *)this + 184) = *((_OWORD *)a2 + 13);
  *((_QWORD *)this + 25) = *((_QWORD *)a2 + 28);
  *((_OWORD *)this - 5) = *(_OWORD *)a2;
  *((_OWORD *)this - 4) = *((_OWORD *)a2 + 1);
  *((_DWORD *)this - 10) = *((_DWORD *)a2 + 10);
  *((_BYTE *)this - 36) = *((_BYTE *)a2 + 44);
  *((_BYTE *)this - 35) = *((_BYTE *)a2 + 45);
  *((_BYTE *)this - 33) = *((_BYTE *)a2 + 46);
  *((_BYTE *)this - 32) = *((_BYTE *)a2 + 47);
  *((_DWORD *)this - 7) = *((_DWORD *)a2 + 12);
  *((_DWORD *)this - 4) = *((_DWORD *)a2 + 16);
  *((_DWORD *)this - 3) = *((_DWORD *)a2 + 17);
  *((_OWORD *)this + 2) = *(_OWORD *)((char *)a2 + 72);
  *((_OWORD *)this + 3) = *(_OWORD *)((char *)a2 + 88);
  *((_DWORD *)this + 16) = *((_DWORD *)a2 + 26);
  v4 = 32;
  if ( *((_DWORD *)a2 + 18) < 0x20u )
    v4 = *((_DWORD *)a2 + 18);
  *((_DWORD *)this + 8) = v4;
  *(_OWORD *)((char *)this + 68) = *(_OWORD *)((char *)a2 + 108);
  *((_DWORD *)this + 21) = *((_DWORD *)a2 + 35);
  *((_BYTE *)this + 88) = *((_BYTE *)a2 + 144);
  *((_BYTE *)this + 89) = *((_BYTE *)a2 + 145);
  *((_DWORD *)this + 23) = *((_DWORD *)a2 + 37);
  *((_DWORD *)this + 24) = *((_DWORD *)a2 + 38);
  *((_DWORD *)this + 25) = *((_DWORD *)a2 + 39);
  *((_DWORD *)this + 26) = *((_DWORD *)a2 + 40);
  *((_DWORD *)this + 27) = *((_DWORD *)a2 + 41);
  result = 0;
  *((_OWORD *)this + 10) = *(_OWORD *)((char *)a2 + 124);
  *(_OWORD *)((char *)this + 116) = *(_OWORD *)((char *)a2 + 168);
  *(_OWORD *)((char *)this + 132) = *(_OWORD *)((char *)a2 + 184);
  return result;
}

```

## disassembly

```asm
0x180059580  mov     [rsp+arg_0], rbx
0x180059585  push    rdi
0x180059586  sub     rsp, 20h
0x18005958a  mov     rdi, rcx
0x18005958d  mov     rbx, rdx
0x180059590  mov     rcx, [rcx-30h]; string
0x180059594  call    cs:__imp_WindowsDeleteString
0x18005959a  mov     qword ptr [rdi-30h], 0
0x1800595a2  mov     rax, [rbx+20h]
0x1800595a6  mov     [rdi-30h], rax
0x1800595aa  mov     qword ptr [rbx+20h], 0
0x1800595b2  mov     rcx, [rdi-18h]; string
0x1800595b6  call    cs:__imp_WindowsDeleteString
0x1800595bc  mov     qword ptr [rdi-18h], 0
0x1800595c4  lea     rdx, [rbx+0C8h]
0x1800595cb  mov     rax, [rbx+38h]
0x1800595cf  lea     rcx, [rdi+98h]
0x1800595d6  mov     [rdi-18h], rax
0x1800595da  mov     qword ptr [rbx+38h], 0
0x1800595e2  call    ??4?$unique_ptr@U_L2_NOTIFICATION_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x1800595e7  movups  xmm0, xmmword ptr [rbx+0D0h]
0x1800595ee  movups  xmmword ptr [rdi+0B8h], xmm0
0x1800595f5  movsd   xmm1, qword ptr [rbx+0E0h]
0x1800595fd  movsd   qword ptr [rdi+0C8h], xmm1
0x180059605  movups  xmm0, xmmword ptr [rbx]
0x180059608  movdqu  xmmword ptr [rdi-50h], xmm0
0x18005960d  movups  xmm1, xmmword ptr [rbx+10h]
0x180059611  movdqu  xmmword ptr [rdi-40h], xmm1
0x180059616  mov     eax, [rbx+28h]
0x180059619  mov     [rdi-28h], eax
0x18005961c  mov     al, [rbx+2Ch]
0x18005961f  mov     [rdi-24h], al
0x180059622  mov     al, [rbx+2Dh]
0x180059625  mov     [rdi-23h], al
0x180059628  mov     al, [rbx+2Eh]
0x18005962b  mov     [rdi-21h], al
0x18005962e  mov     al, [rbx+2Fh]
0x180059631  mov     [rdi-20h], al
0x180059634  mov     eax, [rbx+30h]
0x180059637  mov     [rdi-1Ch], eax
0x18005963a  mov     eax, [rbx+40h]
0x18005963d  mov     [rdi-10h], eax
0x180059640  mov     eax, [rbx+44h]
0x180059643  mov     [rdi-0Ch], eax
0x180059646  movups  xmm0, xmmword ptr [rbx+48h]
0x18005964a  movups  xmmword ptr [rdi+20h], xmm0
0x18005964e  movups  xmm1, xmmword ptr [rbx+58h]
0x180059652  movups  xmmword ptr [rdi+30h], xmm1
0x180059656  mov     eax, [rbx+68h]
0x180059659  mov     [rdi+40h], eax
0x18005965c  mov     eax, 20h ; ' '
0x180059661  cmp     [rbx+48h], eax
0x180059664  cmovb   eax, [rbx+48h]
0x180059668  mov     [rdi+20h], eax
0x18005966b  movups  xmm0, xmmword ptr [rbx+6Ch]
0x18005966f  movdqu  xmmword ptr [rdi+44h], xmm0
0x180059674  mov     eax, [rbx+8Ch]
0x18005967a  mov     [rdi+54h], eax
0x18005967d  mov     al, [rbx+90h]
0x180059683  mov     [rdi+58h], al
0x180059686  mov     al, [rbx+91h]
0x18005968c  mov     [rdi+59h], al
0x18005968f  mov     eax, [rbx+94h]
0x180059695  mov     [rdi+5Ch], eax
0x180059698  mov     eax, [rbx+98h]
0x18005969e  mov     [rdi+60h], eax
0x1800596a1  mov     eax, [rbx+9Ch]
0x1800596a7  mov     [rdi+64h], eax
0x1800596aa  mov     eax, [rbx+0A0h]
0x1800596b0  mov     [rdi+68h], eax
0x1800596b3  mov     eax, [rbx+0A4h]
0x1800596b9  mov     [rdi+6Ch], eax
0x1800596bc  xor     eax, eax
0x1800596be  movups  xmm0, xmmword ptr [rbx+7Ch]
0x1800596c2  movdqu  xmmword ptr [rdi+0A0h], xmm0
0x1800596ca  movups  xmm0, xmmword ptr [rbx+0A8h]
0x1800596d1  movups  xmmword ptr [rdi+74h], xmm0
0x1800596d5  movups  xmm1, xmmword ptr [rbx+0B8h]
0x1800596dc  mov     rbx, [rsp+28h+arg_0]
0x1800596e1  movups  xmmword ptr [rdi+84h], xmm1
0x1800596e8  add     rsp, 20h
0x1800596ec  pop     rdi
0x1800596ed  retn
```
