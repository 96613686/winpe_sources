# SystemSettings::StorageSenseHandlers::AIComponentForLocalService::RuntimeClassInitialize(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,unsigned __int64,unsigned __int64)

- ea: `0x1800c8074`
- end: `0x1800c8191`
- name: `?RuntimeClassInitialize@AIComponentForLocalService@StorageSenseHandlers@SystemSettings@@QEAAJPEAUHSTRING__@@000_K1@Z`
- size: `285`
- prototype: `int(SystemSettings::StorageSenseHandlers::AIComponentForLocalService *__hidden this, HSTRING, HSTRING, HSTRING, HSTRING, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180094088`

## callees

- `0x18000e6cc`
- `0x1800c8074`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c80a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c80f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c8121`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c8153`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c80a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c80f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c8121`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c8153`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c8095`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c80de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c810e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c813e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c8095`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c80de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c810e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c813e`

## string_xrefs

- `0x1800c80be`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\aicomponent.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::StorageSenseHandlers::AIComponentForLocalService::RuntimeClassInitialize(
        HSTRING *this,
        HSTRING a2,
        HSTRING a3,
        HSTRING a4,
        HSTRING string,
        HSTRING a6,
        HSTRING a7)
{
  HSTRING *v7; // rbx
  HRESULT v12; // ebx
  __int64 v13; // rdx
  int v15; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v7 = this + 30;
  WindowsDeleteString(this[30]);
  *v7 = 0;
  v12 = WindowsDuplicateString(a2, v7);
  if ( v12 < 0 )
  {
    v13 = 125;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\aicomponent.cpp",
      (const char *)(unsigned int)v12,
      v15);
    return (unsigned int)v12;
  }
  WindowsDeleteString(this[31]);
  this[31] = 0;
  v12 = WindowsDuplicateString(a3, this + 31);
  if ( v12 < 0 )
  {
    v13 = 126;
    goto LABEL_3;
  }
  WindowsDeleteString(this[32]);
  this[32] = 0;
  v12 = WindowsDuplicateString(a4, this + 32);
  if ( v12 < 0 )
  {
    v13 = 127;
    goto LABEL_3;
  }
  WindowsDeleteString(this[33]);
  this[33] = 0;
  v12 = WindowsDuplicateString(string, this + 33);
  if ( v12 < 0 )
  {
    v13 = 128;
    goto LABEL_3;
  }
  this[34] = a6;
  this[35] = a7;
  return 0;
}

```

## disassembly

```asm
0x1800c8074  push    rbx
0x1800c8076  push    rbp
0x1800c8077  push    rsi
0x1800c8078  push    rdi
0x1800c8079  push    r14; int
0x1800c807b  sub     rsp, 20h
0x1800c807f  lea     rbx, [rcx+0F0h]
0x1800c8086  mov     rsi, rcx
0x1800c8089  mov     rcx, [rbx]; string
0x1800c808c  mov     r14, r9
0x1800c808f  mov     rbp, r8
0x1800c8092  mov     rdi, rdx
0x1800c8095  call    cs:__imp_WindowsDeleteString
0x1800c809b  mov     rdx, rbx; newString
0x1800c809e  mov     qword ptr [rbx], 0
0x1800c80a5  mov     rcx, rdi; string
0x1800c80a8  call    cs:__imp_WindowsDuplicateString
0x1800c80ae  mov     ebx, eax
0x1800c80b0  test    eax, eax
0x1800c80b2  jns     short loc_1800C80D4
0x1800c80b4  mov     edx, 7Dh ; '}'; void *
0x1800c80b9  mov     rcx, [rsp+48h]; this
0x1800c80be  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\coresettinghandlers"...
0x1800c80c5  mov     r9d, ebx; char *
0x1800c80c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c80cd  mov     eax, ebx
0x1800c80cf  jmp     loc_1800C8186
0x1800c80d4  lea     rbx, [rsi+0F8h]
0x1800c80db  mov     rcx, [rbx]; string
0x1800c80de  call    cs:__imp_WindowsDeleteString
0x1800c80e4  mov     rdx, rbx; newString
0x1800c80e7  mov     qword ptr [rbx], 0
0x1800c80ee  mov     rcx, rbp; string
0x1800c80f1  call    cs:__imp_WindowsDuplicateString
0x1800c80f7  mov     ebx, eax
0x1800c80f9  test    eax, eax
0x1800c80fb  jns     short loc_1800C8104
0x1800c80fd  mov     edx, 7Eh ; '~'
0x1800c8102  jmp     short loc_1800C80B9
0x1800c8104  lea     rbx, [rsi+100h]
0x1800c810b  mov     rcx, [rbx]; string
0x1800c810e  call    cs:__imp_WindowsDeleteString
0x1800c8114  mov     rdx, rbx; newString
0x1800c8117  mov     qword ptr [rbx], 0
0x1800c811e  mov     rcx, r14; string
0x1800c8121  call    cs:__imp_WindowsDuplicateString
0x1800c8127  mov     ebx, eax
0x1800c8129  test    eax, eax
0x1800c812b  jns     short loc_1800C8134
0x1800c812d  mov     edx, 7Fh
0x1800c8132  jmp     short loc_1800C80B9
0x1800c8134  lea     rbx, [rsi+108h]
0x1800c813b  mov     rcx, [rbx]; string
0x1800c813e  call    cs:__imp_WindowsDeleteString
0x1800c8144  mov     rcx, [rsp+48h+string]; string
0x1800c8149  mov     rdx, rbx; newString
0x1800c814c  mov     qword ptr [rbx], 0
0x1800c8153  call    cs:__imp_WindowsDuplicateString
0x1800c8159  mov     ebx, eax
0x1800c815b  test    eax, eax
0x1800c815d  jns     short loc_1800C8169
0x1800c815f  mov     edx, 80h
0x1800c8164  jmp     loc_1800C80B9
0x1800c8169  mov     rax, [rsp+48h+arg_28]
0x1800c816e  mov     [rsi+110h], rax
0x1800c8175  mov     rax, [rsp+48h+arg_30]
0x1800c817d  mov     [rsi+118h], rax
0x1800c8184  xor     eax, eax
0x1800c8186  add     rsp, 20h
0x1800c818a  pop     r14
0x1800c818c  pop     rdi
0x1800c818d  pop     rsi
0x1800c818e  pop     rbp
0x1800c818f  pop     rbx
0x1800c8190  retn
```
