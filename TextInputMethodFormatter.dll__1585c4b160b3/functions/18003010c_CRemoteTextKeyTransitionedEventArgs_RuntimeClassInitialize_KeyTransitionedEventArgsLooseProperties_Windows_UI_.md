# CRemoteTextKeyTransitionedEventArgs::RuntimeClassInitialize(KeyTransitionedEventArgsLooseProperties,Windows::UI::Internal::Text::Remote::RemoteTextKeyEventHostInfo,uint,uchar *,HSTRING__ *,HSTRING__ *)

- ea: `0x18003010c`
- end: `0x18003021d`
- name: `?RuntimeClassInitialize@CRemoteTextKeyTransitionedEventArgs@@QEAAJUKeyTransitionedEventArgsLooseProperties@@URemoteTextKeyEventHostInfo@Remote@Text@Internal@UI@Windows@@IPEAEPEAUHSTRING__@@3@Z`
- size: `273`
- prototype: `int __high(struct KeyTransitionedEventArgsLooseProperties, struct Windows::UI::Internal::Text::Remote::RemoteTextKeyEventHostInfo, unsigned int, unsigned __int8 *, HSTRING, HSTRING)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018f2c`

## callees

- `0x180003345`
- `0x18003010c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800301ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800301f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800301ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800301f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800301c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003020b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800301c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003020b`

## pseudocode

```c
__int64 __fastcall CRemoteTextKeyTransitionedEventArgs::RuntimeClassInitialize(
        __int64 a1,
        int *a2,
        __int64 a3,
        unsigned int a4,
        void *Src,
        HSTRING string,
        HSTRING a7)
{
  int v7; // eax
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  int v12; // eax
  int v13; // eax
  __int128 v14; // xmm1
  int v15; // eax
  HSTRING *v16; // rdi

  v7 = *a2;
  v10 = *(_OWORD *)(a3 + 16);
  *(_OWORD *)(a1 + 88) = *(_OWORD *)a3;
  *(_DWORD *)(a1 + 64) = v7;
  v11 = *(_OWORD *)(a3 + 32);
  *(_DWORD *)(a1 + 68) = a2[1];
  v12 = a2[2];
  *(_OWORD *)(a1 + 104) = v10;
  *(_DWORD *)(a1 + 72) = v12;
  v13 = a2[3];
  v14 = *(_OWORD *)(a3 + 48);
  *(_OWORD *)(a1 + 120) = v11;
  *(_DWORD *)(a1 + 76) = v13;
  *(_QWORD *)&v11 = *(_QWORD *)(a3 + 64);
  *(_DWORD *)(a1 + 80) = a2[4];
  v15 = a2[5];
  *(_OWORD *)(a1 + 136) = v14;
  *(_QWORD *)(a1 + 168) = Src;
  *(_DWORD *)(a1 + 84) = v15;
  *(_QWORD *)(a1 + 152) = v11;
  *(_DWORD *)(a1 + 160) = a4;
  memcpy_0((void *)(a1 + 176), Src, a4);
  v16 = (HSTRING *)(a1 + 432);
  if ( !string || string != *v16 )
  {
    WindowsDeleteString(*v16);
    *v16 = 0;
    WindowsDuplicateString(string, (HSTRING *)(a1 + 432));
  }
  *(_WORD *)(a1 + 440) = *((_WORD *)a2 + 12);
  if ( !a7 || a7 != *(HSTRING *)(a1 + 448) )
  {
    WindowsDeleteString(*(HSTRING *)(a1 + 448));
    *(_QWORD *)(a1 + 448) = 0;
    WindowsDuplicateString(a7, (HSTRING *)(a1 + 448));
  }
  return 0;
}

```

## disassembly

```asm
0x18003010c  push    rbx
0x18003010e  push    rsi
0x18003010f  push    rdi
0x180030110  push    r14
0x180030112  sub     rsp, 28h
0x180030116  mov     eax, [rdx]
0x180030118  mov     r14, rdx
0x18003011b  movaps  xmm0, xmmword ptr [r8]
0x18003011f  mov     rbx, rcx
0x180030122  movaps  xmm1, xmmword ptr [r8+10h]
0x180030127  movups  xmmword ptr [rcx+58h], xmm0
0x18003012b  mov     [rcx+40h], eax
0x18003012e  mov     eax, [rdx+4]
0x180030131  movaps  xmm0, xmmword ptr [r8+20h]
0x180030136  mov     [rcx+44h], eax
0x180030139  mov     eax, [rdx+8]
0x18003013c  movups  xmmword ptr [rcx+68h], xmm1
0x180030140  mov     [rcx+48h], eax
0x180030143  mov     eax, [rdx+0Ch]
0x180030146  movaps  xmm1, xmmword ptr [r8+30h]
0x18003014b  movups  xmmword ptr [rcx+78h], xmm0
0x18003014f  mov     [rcx+4Ch], eax
0x180030152  mov     eax, [rdx+10h]
0x180030155  movsd   xmm0, qword ptr [r8+40h]
0x18003015b  mov     [rcx+50h], eax
0x18003015e  mov     eax, [rdx+14h]
0x180030161  mov     rdx, [rsp+48h+Src]; Src
0x180030166  movups  xmmword ptr [rcx+88h], xmm1
0x18003016d  mov     [rcx+0A8h], rdx
0x180030174  mov     [rcx+54h], eax
0x180030177  movsd   qword ptr [rcx+98h], xmm0
0x18003017f  mov     [rcx+0A0h], r9d
0x180030186  add     rcx, 0B0h; void *
0x18003018d  mov     r8d, r9d; Size
0x180030190  call    memcpy_0
0x180030195  mov     rsi, [rsp+48h+string]
0x18003019a  lea     rdi, [rbx+1B0h]
0x1800301a1  test    rsi, rsi
0x1800301a4  jz      short loc_1800301AB
0x1800301a6  cmp     rsi, [rdi]
0x1800301a9  jz      short loc_1800301C7
0x1800301ab  mov     rcx, [rdi]; string
0x1800301ae  call    cs:__imp_WindowsDeleteString
0x1800301b4  mov     rdx, rdi; newString
0x1800301b7  mov     qword ptr [rdi], 0
0x1800301be  mov     rcx, rsi; string
0x1800301c1  call    cs:__imp_WindowsDuplicateString
0x1800301c7  mov     rdi, [rsp+48h+arg_30]
0x1800301cf  movzx   eax, word ptr [r14+18h]
0x1800301d4  mov     [rbx+1B8h], ax
0x1800301db  test    rdi, rdi
0x1800301de  jz      short loc_1800301E9
0x1800301e0  cmp     rdi, [rbx+1C0h]
0x1800301e7  jz      short loc_180030211
0x1800301e9  mov     rcx, [rbx+1C0h]; string
0x1800301f0  call    cs:__imp_WindowsDeleteString
0x1800301f6  lea     rdx, [rbx+1C0h]; newString
0x1800301fd  mov     qword ptr [rbx+1C0h], 0
0x180030208  mov     rcx, rdi; string
0x18003020b  call    cs:__imp_WindowsDuplicateString
0x180030211  xor     eax, eax
0x180030213  add     rsp, 28h
0x180030217  pop     r14
0x180030219  pop     rdi
0x18003021a  pop     rsi
0x18003021b  pop     rbx
0x18003021c  retn
```
