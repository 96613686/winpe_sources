# sub_1800EACF4

- ea: `0x1800eacf4`
- end: `0x1800eaf7f`
- name: `sub_1800EACF4`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1800eb00c`

## callees

- `0x18005815c`
- `0x1800587d8`
- `0x1800da304`
- `0x1800e9a24`
- `0x1800e9f10`
- `0x1800ea664`
- `0x1800ea680`
- `0x1800eab9c`
- `0x1800eacf4`
- `0x1800eaf80`
- `0x180271a30`

## import_xrefs

- `KERNEL32!SetThreadpoolWait` at `0x1800eaec5`
- `KERNEL32!SetThreadpoolWait` at `0x1800eaf5c`
- `KERNEL32!SetThreadpoolWait` at `0x1800eaec5`
- `KERNEL32!SetThreadpoolWait` at `0x1800eaf5c`
- `KERNEL32!CreateThreadpoolWait` at `0x1800eaea0`
- `KERNEL32!CreateThreadpoolWait` at `0x1800eaea0`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x1800eaed3`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x1800eaed3`
- `KERNEL32!CloseThreadpoolWait` at `0x1800eaedc`
- `KERNEL32!CloseThreadpoolWait` at `0x1800eaedc`
- `KERNEL32!CreateEventExW` at `0x1800eade9`
- `KERNEL32!CreateEventExW` at `0x1800eade9`
- `KERNEL32!GetLastError` at `0x1800eadf7`
- `KERNEL32!GetLastError` at `0x1800eae09`
- `KERNEL32!GetLastError` at `0x1800eaeb5`
- `KERNEL32!GetLastError` at `0x1800eaf30`
- `KERNEL32!GetLastError` at `0x1800eadf7`
- `KERNEL32!GetLastError` at `0x1800eae09`
- `KERNEL32!GetLastError` at `0x1800eaeb5`
- `KERNEL32!GetLastError` at `0x1800eaf30`
- `KERNEL32!CloseHandle` at `0x1800eae14`
- `KERNEL32!CloseHandle` at `0x1800eae14`
- `KERNEL32!SetLastError` at `0x1800eae24`
- `KERNEL32!SetLastError` at `0x1800eaee4`
- `KERNEL32!SetLastError` at `0x1800eaf42`
- `KERNEL32!SetLastError` at `0x1800eae24`
- `KERNEL32!SetLastError` at `0x1800eaee4`
- `KERNEL32!SetLastError` at `0x1800eaf42`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x1800eae51`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x1800eae51`

## string_xrefs

- `0x1800eadc4`: `src\epp\Dlp\EndpointDlp\inc\wil\registryDlp.h`
- `0x1800eae80`: `src\epp\Dlp\EndpointDlp\inc\wil\registryDlp.h`
- `0x1800eaefb`: `src\epp\Dlp\EndpointDlp\inc\wil\registryDlp.h`

## pseudocode

```c
__int64 __fastcall sub_1800EACF4(void **a1, _QWORD *a2, char a3, __int64 a4)
{
  __int64 v8; // rax
  __int64 v9; // rdi
  unsigned int v10; // ebx
  HANDLE Event; // rsi
  void *v13; // rbx
  DWORD LastError; // ebp
  unsigned int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned int v18; // eax
  int v19; // eax
  PTP_WAIT ThreadpoolWait; // rsi
  struct _TP_WAIT *v21; // rbp
  DWORD v22; // ebx
  void *v23; // rsi
  DWORD v24; // ebx
  void *retaddr; // [rsp+68h] [rbp+0h]

  v8 = sub_1800587D8(160, &qword_18029F090);
  v9 = v8;
  if ( v8 )
  {
    if ( *(_QWORD *)(a4 + 112) )
    {
      *(_QWORD *)(v8 + 112) = v8 + 8;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a4 + 112) + 16LL))(*(_QWORD *)(a4 + 112));
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a4 + 112) + 24LL))(*(_QWORD *)(a4 + 112));
      *(_QWORD *)(a4 + 112) = 0;
    }
    else
    {
      *(_QWORD *)(v8 + 112) = 0;
    }
    *(_QWORD *)(v9 + 120) = *a2;
    *a2 = 0;
    *(_QWORD *)(v9 + 128) = 0;
    *(_QWORD *)(v9 + 136) = 0;
    *(_BYTE *)(v9 + 144) = a3;
    *(_DWORD *)(v9 + 148) = 1;
    *(_QWORD *)(v9 + 152) = 0;
  }
  else
  {
    v9 = 0;
  }
  if ( !v9 )
  {
    v10 = -2147024882;
    sub_1800DA304(retaddr, 234, "src\\epp\\Dlp\\EndpointDlp\\inc\\wil\\registryDlp.h", 2147942414LL);
    return v10;
  }
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    v13 = *(void **)(v9 + 128);
    if ( v13 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v13) )
        sub_1800EAB9C(retaddr, 2366);
      SetLastError(LastError);
    }
    *(_QWORD *)(v9 + 128) = Event;
  }
  else
  {
    v19 = sub_1800E9F10();
    v10 = v19;
    if ( v19 < 0 )
    {
      sub_1800DA304(retaddr, 235, "src\\epp\\Dlp\\EndpointDlp\\inc\\wil\\registryDlp.h", (unsigned int)v19);
LABEL_24:
      sub_1800E9A24(v9);
      sub_18005815C((LPVOID)v9);
      return v10;
    }
  }
  v15 = RegNotifyChangeKeyValue(
          *(HKEY *)(v9 + 120),
          *(unsigned __int8 *)(v9 + 144),
          0x10000005u,
          *(HANDLE *)(v9 + 128),
          1);
  if ( v15 )
  {
    v18 = sub_1800EA680(retaddr, v16, v17, v15);
LABEL_23:
    v10 = v18;
    goto LABEL_24;
  }
  ThreadpoolWait = CreateThreadpoolWait(pfnwa, (PVOID)v9, 0);
  v21 = *(struct _TP_WAIT **)(v9 + 136);
  if ( v21 )
  {
    v22 = GetLastError();
    SetThreadpoolWait(v21, 0, 0);
    WaitForThreadpoolWaitCallbacks(v21, 1);
    CloseThreadpoolWait(v21);
    SetLastError(v22);
  }
  *(_QWORD *)(v9 + 136) = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    v18 = sub_1800EA664(retaddr, 241, "src\\epp\\Dlp\\EndpointDlp\\inc\\wil\\registryDlp.h");
    goto LABEL_23;
  }
  v23 = *a1;
  if ( *a1 )
  {
    v24 = GetLastError();
    sub_1800EAF80(v23);
    SetLastError(v24);
  }
  *a1 = (void *)v9;
  SetThreadpoolWait(*(PTP_WAIT *)(v9 + 136), *(HANDLE *)(v9 + 128), 0);
  return 0;
}

```

## disassembly

```asm
0x1800eacf4  push    rbx
0x1800eacf6  push    rbp
0x1800eacf7  push    rsi
0x1800eacf8  push    rdi
0x1800eacf9  push    r14
0x1800eacfb  sub     rsp, 40h
0x1800eacff  mov     rbx, r9
0x1800ead02  mov     bpl, r8b
0x1800ead05  mov     rsi, rdx
0x1800ead08  mov     r14, rcx
0x1800ead0b  lea     rdx, qword_18029F090
0x1800ead12  mov     ecx, 0A0h
0x1800ead17  call    sub_1800587D8
0x1800ead1c  mov     rdi, rax
0x1800ead1f  mov     [rsp+68h+var_38], rax
0x1800ead24  test    rax, rax
0x1800ead27  jz      loc_1800EADB0
0x1800ead2d  cmp     qword ptr [rbx+70h], 0
0x1800ead32  jnz     short loc_1800EAD3E
0x1800ead34  mov     qword ptr [rax+70h], 0
0x1800ead3c  jmp     short loc_1800EAD70
0x1800ead3e  lea     rdx, [rax+8]
0x1800ead42  mov     [rax+70h], rdx
0x1800ead46  mov     rcx, [rbx+70h]
0x1800ead4a  mov     rax, [rcx]
0x1800ead4d  mov     rax, [rax+10h]
0x1800ead51  call    cs:__guard_dispatch_icall_fptr
0x1800ead57  mov     rcx, [rbx+70h]
0x1800ead5b  mov     rax, [rcx]
0x1800ead5e  mov     rax, [rax+18h]
0x1800ead62  call    cs:__guard_dispatch_icall_fptr
0x1800ead68  mov     qword ptr [rbx+70h], 0
0x1800ead70  mov     rax, [rsi]
0x1800ead73  mov     [rdi+78h], rax
0x1800ead77  mov     qword ptr [rsi], 0
0x1800ead7e  mov     qword ptr [rdi+80h], 0
0x1800ead89  mov     qword ptr [rdi+88h], 0
0x1800ead94  mov     [rdi+90h], bpl
0x1800ead9b  mov     dword ptr [rdi+94h], 1
0x1800eada5  xor     eax, eax
0x1800eada7  mov     [rdi+98h], rax
0x1800eadae  jmp     short loc_1800EADB2
0x1800eadb0  xor     edi, edi
0x1800eadb2  test    rdi, rdi
0x1800eadb5  jnz     short loc_1800EADDC
0x1800eadb7  mov     rcx, [rsp+68h]
0x1800eadbc  mov     ebx, 8007000Eh
0x1800eadc1  mov     r9d, ebx
0x1800eadc4  lea     r8, aSrcEppDlpEndpo_2; "src\\epp\\Dlp\\EndpointDlp\\inc\\wil\\r"...
0x1800eadcb  mov     edx, 0EAh
0x1800eadd0  call    sub_1800DA304
0x1800eadd5  mov     eax, ebx
0x1800eadd7  jmp     loc_1800EAF64
0x1800eaddc  mov     r9d, 1F0003h; dwDesiredAccess
0x1800eade2  xor     r8d, r8d; dwFlags
0x1800eade5  xor     edx, edx; lpName
0x1800eade7  xor     ecx, ecx; lpEventAttributes
0x1800eade9  call    cs:CreateEventExW
0x1800eadef  mov     rsi, rax
0x1800eadf2  test    rax, rax
0x1800eadf5  jz      short loc_1800EAE6D
0x1800eadf7  call    cs:GetLastError
0x1800eadfd  mov     rbx, [rdi+80h]
0x1800eae04  test    rbx, rbx
0x1800eae07  jz      short loc_1800EAE2A
0x1800eae09  call    cs:GetLastError
0x1800eae0f  mov     ebp, eax
0x1800eae11  mov     rcx, rbx; hObject
0x1800eae14  call    cs:CloseHandle
0x1800eae1a  test    eax, eax
0x1800eae1c  jz      loc_1800EAF6F
0x1800eae22  mov     ecx, ebp; dwErrCode
0x1800eae24  call    cs:SetLastError
0x1800eae2a  mov     [rdi+80h], rsi
0x1800eae31  movzx   edx, byte ptr [rdi+90h]; bWatchSubtree
0x1800eae38  mov     [rsp+68h+fAsynchronous], 1; fAsynchronous
0x1800eae40  mov     r9, [rdi+80h]; hEvent
0x1800eae47  mov     r8d, 10000005h; dwNotifyFilter
0x1800eae4d  mov     rcx, [rdi+78h]; hKey
0x1800eae51  call    cs:RegNotifyChangeKeyValue
0x1800eae57  test    eax, eax
0x1800eae59  jz      short loc_1800EAE93
0x1800eae5b  mov     rcx, [rsp+68h]
0x1800eae60  mov     r9d, eax
0x1800eae63  call    sub_1800EA680
0x1800eae68  jmp     loc_1800EAF0C
0x1800eae6d  call    sub_1800E9F10
0x1800eae72  mov     ebx, eax
0x1800eae74  test    eax, eax
0x1800eae76  jns     short loc_1800EAE31
0x1800eae78  mov     rcx, [rsp+68h]
0x1800eae7d  mov     r9d, eax
0x1800eae80  lea     r8, aSrcEppDlpEndpo_2; "src\\epp\\Dlp\\EndpointDlp\\inc\\wil\\r"...
0x1800eae87  mov     edx, 0EBh
0x1800eae8c  call    sub_1800DA304
0x1800eae91  jmp     short loc_1800EAF0E
0x1800eae93  xor     r8d, r8d; pcbe
0x1800eae96  mov     rdx, rdi; pv
0x1800eae99  lea     rcx, pfnwa; pfnwa
0x1800eaea0  call    cs:CreateThreadpoolWait
0x1800eaea6  mov     rsi, rax
0x1800eaea9  mov     rbp, [rdi+88h]
0x1800eaeb0  test    rbp, rbp
0x1800eaeb3  jz      short loc_1800EAEEA
0x1800eaeb5  call    cs:GetLastError
0x1800eaebb  mov     ebx, eax
0x1800eaebd  xor     r8d, r8d; pftTimeout
0x1800eaec0  xor     edx, edx; h
0x1800eaec2  mov     rcx, rbp; pwa
0x1800eaec5  call    cs:SetThreadpoolWait
0x1800eaecb  mov     edx, 1; fCancelPendingCallbacks
0x1800eaed0  mov     rcx, rbp; pwa
0x1800eaed3  call    cs:WaitForThreadpoolWaitCallbacks
0x1800eaed9  mov     rcx, rbp; pwa
0x1800eaedc  call    cs:CloseThreadpoolWait
0x1800eaee2  mov     ecx, ebx; dwErrCode
0x1800eaee4  call    cs:SetLastError
0x1800eaeea  mov     [rdi+88h], rsi
0x1800eaef1  test    rsi, rsi
0x1800eaef4  jnz     short loc_1800EAF28
0x1800eaef6  mov     rcx, [rsp+68h]
0x1800eaefb  lea     r8, aSrcEppDlpEndpo_2; "src\\epp\\Dlp\\EndpointDlp\\inc\\wil\\r"...
0x1800eaf02  mov     edx, 0F1h
0x1800eaf07  call    sub_1800EA664
0x1800eaf0c  mov     ebx, eax
0x1800eaf0e  mov     rcx, rdi
0x1800eaf11  call    sub_1800E9A24
0x1800eaf16  mov     edx, 0A0h
0x1800eaf1b  mov     rcx, rdi; lpMem
0x1800eaf1e  call    sub_18005815C
0x1800eaf23  jmp     loc_1800EADD5
0x1800eaf28  mov     rsi, [r14]
0x1800eaf2b  test    rsi, rsi
0x1800eaf2e  jz      short loc_1800EAF48
0x1800eaf30  call    cs:GetLastError
0x1800eaf36  mov     ebx, eax
0x1800eaf38  mov     rcx, rsi; lpMem
0x1800eaf3b  call    sub_1800EAF80
0x1800eaf40  mov     ecx, ebx; dwErrCode
0x1800eaf42  call    cs:SetLastError
0x1800eaf48  mov     [r14], rdi
0x1800eaf4b  xor     r8d, r8d; pftTimeout
0x1800eaf4e  mov     rdx, [rdi+80h]; h
0x1800eaf55  mov     rcx, [rdi+88h]; pwa
0x1800eaf5c  call    cs:SetThreadpoolWait
0x1800eaf62  xor     eax, eax
0x1800eaf64  add     rsp, 40h
0x1800eaf68  pop     r14
0x1800eaf6a  pop     rdi
0x1800eaf6b  pop     rsi
0x1800eaf6c  pop     rbp
0x1800eaf6d  pop     rbx
0x1800eaf6e  retn
0x1800eaf6f  mov     rcx, [rsp+68h]
0x1800eaf74  mov     edx, 93Eh
0x1800eaf79  call    sub_1800EAB9C
```
