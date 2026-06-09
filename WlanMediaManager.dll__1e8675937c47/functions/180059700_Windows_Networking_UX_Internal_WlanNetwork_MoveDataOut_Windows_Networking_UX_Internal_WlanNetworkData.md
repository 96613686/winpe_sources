# Windows::Networking::UX::Internal::WlanNetwork::MoveDataOut(Windows::Networking::UX::Internal::WlanNetworkData *)

- ea: `0x180059700`
- end: `0x18005986e`
- name: `?MoveDataOut@WlanNetwork@Internal@UX@Networking@Windows@@UEAAJPEAUWlanNetworkData@2345@@Z`
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

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059714`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059736`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059714`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059736`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::WlanNetwork::MoveDataOut(
        Windows::Networking::UX::Internal::WlanNetwork *this,
        struct Windows::Networking::UX::Internal::WlanNetworkData *a2)
{
  int v4; // eax
  __int64 result; // rax

  WindowsDeleteString(*((HSTRING *)a2 + 4));
  *((_QWORD *)a2 + 4) = 0;
  *((_QWORD *)a2 + 4) = *((_QWORD *)this - 6);
  *((_QWORD *)this - 6) = 0;
  WindowsDeleteString(*((HSTRING *)a2 + 7));
  *((_QWORD *)a2 + 7) = 0;
  *((_QWORD *)a2 + 7) = *((_QWORD *)this - 3);
  *((_QWORD *)this - 3) = 0;
  wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
    (char *)a2 + 200,
    (char *)this + 152);
  *((_OWORD *)a2 + 13) = *(_OWORD *)((char *)this + 184);
  *((_QWORD *)a2 + 28) = *((_QWORD *)this + 25);
  *(_OWORD *)a2 = *((_OWORD *)this - 5);
  *((_OWORD *)a2 + 1) = *((_OWORD *)this - 4);
  *((_DWORD *)a2 + 10) = *((_DWORD *)this - 10);
  *((_BYTE *)a2 + 44) = *((_BYTE *)this - 36);
  *((_BYTE *)a2 + 45) = *((_BYTE *)this - 35);
  *((_BYTE *)a2 + 46) = *((_BYTE *)this - 33);
  *((_BYTE *)a2 + 47) = *((_BYTE *)this - 32);
  *((_DWORD *)a2 + 12) = *((_DWORD *)this - 7);
  *((_DWORD *)a2 + 16) = *((_DWORD *)this - 4);
  *((_DWORD *)a2 + 17) = *((_DWORD *)this - 3);
  *(_OWORD *)((char *)a2 + 72) = *((_OWORD *)this + 2);
  *(_OWORD *)((char *)a2 + 88) = *((_OWORD *)this + 3);
  *((_DWORD *)a2 + 26) = *((_DWORD *)this + 16);
  v4 = 32;
  if ( *((_DWORD *)this + 8) < 0x20u )
    v4 = *((_DWORD *)this + 8);
  *((_DWORD *)a2 + 18) = v4;
  *(_OWORD *)((char *)a2 + 108) = *(_OWORD *)((char *)this + 68);
  *((_DWORD *)a2 + 35) = *((_DWORD *)this + 21);
  *((_BYTE *)a2 + 144) = *((_BYTE *)this + 88);
  *((_BYTE *)a2 + 145) = *((_BYTE *)this + 89);
  *((_DWORD *)a2 + 37) = *((_DWORD *)this + 23);
  *((_DWORD *)a2 + 38) = *((_DWORD *)this + 24);
  *((_DWORD *)a2 + 39) = *((_DWORD *)this + 25);
  *((_DWORD *)a2 + 40) = *((_DWORD *)this + 26);
  *((_DWORD *)a2 + 41) = *((_DWORD *)this + 27);
  result = 0;
  *(_OWORD *)((char *)a2 + 124) = *((_OWORD *)this + 10);
  *(_OWORD *)((char *)a2 + 168) = *(_OWORD *)((char *)this + 116);
  *(_OWORD *)((char *)a2 + 184) = *(_OWORD *)((char *)this + 132);
  return result;
}

```

## disassembly

```asm
0x180059700  mov     [rsp+arg_0], rbx
0x180059705  push    rdi
0x180059706  sub     rsp, 20h
0x18005970a  mov     rbx, rcx
0x18005970d  mov     rdi, rdx
0x180059710  mov     rcx, [rdx+20h]; string
0x180059714  call    cs:__imp_WindowsDeleteString
0x18005971a  mov     qword ptr [rdi+20h], 0
0x180059722  mov     rax, [rbx-30h]
0x180059726  mov     [rdi+20h], rax
0x18005972a  mov     qword ptr [rbx-30h], 0
0x180059732  mov     rcx, [rdi+38h]; string
0x180059736  call    cs:__imp_WindowsDeleteString
0x18005973c  mov     qword ptr [rdi+38h], 0
0x180059744  lea     rdx, [rbx+98h]
0x18005974b  mov     rax, [rbx-18h]
0x18005974f  lea     rcx, [rdi+0C8h]
0x180059756  mov     [rdi+38h], rax
0x18005975a  mov     qword ptr [rbx-18h], 0
0x180059762  call    ??4?$unique_ptr@U_L2_NOTIFICATION_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x180059767  movups  xmm0, xmmword ptr [rbx+0B8h]
0x18005976e  movups  xmmword ptr [rdi+0D0h], xmm0
0x180059775  movsd   xmm1, qword ptr [rbx+0C8h]
0x18005977d  movsd   qword ptr [rdi+0E0h], xmm1
0x180059785  movups  xmm0, xmmword ptr [rbx-50h]
0x180059789  movdqu  xmmword ptr [rdi], xmm0
0x18005978d  movups  xmm1, xmmword ptr [rbx-40h]
0x180059791  movdqu  xmmword ptr [rdi+10h], xmm1
0x180059796  mov     eax, [rbx-28h]
0x180059799  mov     [rdi+28h], eax
0x18005979c  mov     al, [rbx-24h]
0x18005979f  mov     [rdi+2Ch], al
0x1800597a2  mov     al, [rbx-23h]
0x1800597a5  mov     [rdi+2Dh], al
0x1800597a8  mov     al, [rbx-21h]
0x1800597ab  mov     [rdi+2Eh], al
0x1800597ae  mov     al, [rbx-20h]
0x1800597b1  mov     [rdi+2Fh], al
0x1800597b4  mov     eax, [rbx-1Ch]
0x1800597b7  mov     [rdi+30h], eax
0x1800597ba  mov     eax, [rbx-10h]
0x1800597bd  mov     [rdi+40h], eax
0x1800597c0  mov     eax, [rbx-0Ch]
0x1800597c3  mov     [rdi+44h], eax
0x1800597c6  movups  xmm0, xmmword ptr [rbx+20h]
0x1800597ca  movups  xmmword ptr [rdi+48h], xmm0
0x1800597ce  movups  xmm1, xmmword ptr [rbx+30h]
0x1800597d2  movups  xmmword ptr [rdi+58h], xmm1
0x1800597d6  mov     eax, [rbx+40h]
0x1800597d9  mov     [rdi+68h], eax
0x1800597dc  mov     eax, 20h ; ' '
0x1800597e1  cmp     [rbx+20h], eax
0x1800597e4  cmovb   eax, [rbx+20h]
0x1800597e8  mov     [rdi+48h], eax
0x1800597eb  movups  xmm0, xmmword ptr [rbx+44h]
0x1800597ef  movdqu  xmmword ptr [rdi+6Ch], xmm0
0x1800597f4  mov     eax, [rbx+54h]
0x1800597f7  mov     [rdi+8Ch], eax
0x1800597fd  mov     al, [rbx+58h]
0x180059800  mov     [rdi+90h], al
0x180059806  mov     al, [rbx+59h]
0x180059809  mov     [rdi+91h], al
0x18005980f  mov     eax, [rbx+5Ch]
0x180059812  mov     [rdi+94h], eax
0x180059818  mov     eax, [rbx+60h]
0x18005981b  mov     [rdi+98h], eax
0x180059821  mov     eax, [rbx+64h]
0x180059824  mov     [rdi+9Ch], eax
0x18005982a  mov     eax, [rbx+68h]
0x18005982d  mov     [rdi+0A0h], eax
0x180059833  mov     eax, [rbx+6Ch]
0x180059836  mov     [rdi+0A4h], eax
0x18005983c  xor     eax, eax
0x18005983e  movups  xmm0, xmmword ptr [rbx+0A0h]
0x180059845  movdqu  xmmword ptr [rdi+7Ch], xmm0
0x18005984a  movups  xmm0, xmmword ptr [rbx+74h]
0x18005984e  movups  xmmword ptr [rdi+0A8h], xmm0
0x180059855  movups  xmm1, xmmword ptr [rbx+84h]
0x18005985c  mov     rbx, [rsp+28h+arg_0]
0x180059861  movups  xmmword ptr [rdi+0B8h], xmm1
0x180059868  add     rsp, 20h
0x18005986c  pop     rdi
0x18005986d  retn
```
