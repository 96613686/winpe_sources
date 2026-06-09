# NotificationQueueManager::NotificationProcessingShouldBeDeferred(TileNotificationManager *)

- ea: `0x1801d98b0`
- end: `0x1801d99eb`
- name: `?NotificationProcessingShouldBeDeferred@NotificationQueueManager@@AEAA_NPEAVTileNotificationManager@@@Z`
- size: `315`
- prototype: `bool __fastcall(NotificationQueueManager *__hidden this, struct TileNotificationManager *)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180163570`
- `0x180163750`
- `0x180163920`

## callees

- `0x180161204`
- `0x1801d98b0`
- `0x1801d9a00`
- `0x18027f278`
- `0x180283060`
- `0x180283590`
- `0x180288a40`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d98d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d9947`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d9965`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d99b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d99c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d99d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d98d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d9947`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d9965`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d99b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d99c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d99d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d9988`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d9998`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d9988`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d9998`

## string_xrefs

- `0x1801d98f4`: `shellcommon\shell\tiles\sharedmodel\notificationqueuemanager\lib\notificationqueuemanager.cpp`

## pseudocode

```c
char __fastcall NotificationQueueManager::NotificationProcessingShouldBeDeferred(
        NotificationQueueManager *this,
        struct TileNotificationManager *a2)
{
  int NotificationId; // eax
  char v5; // bl
  HSTRING v6; // rcx
  HSTRING v8; // [rsp+20h] [rbp-20h] BYREF
  PCWSTR StringRawBuffer; // [rsp+28h] [rbp-18h] BYREF
  PCWSTR v10[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  HSTRING string; // [rsp+60h] [rbp+20h] BYREF
  HSTRING v13; // [rsp+68h] [rbp+28h] BYREF

  WindowsDeleteString(0);
  v8 = 0;
  NotificationId = TileNotificationManager::GetNotificationId(a2, &v8);
  if ( NotificationId >= 0 )
  {
    if ( *((_BYTE *)this + 232)
      || std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,bool,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,bool>>,0>>::count(
           (char *)this + 96,
           &v8) )
    {
      v5 = 0;
    }
    else
    {
      v5 = 1;
      if ( !*((_BYTE *)a2 + 118) )
      {
        v13 = 0;
        string = 0;
        WindowsDeleteString(0);
        v13 = 0;
        TileNotificationManager::GetApplicationUserModelId(a2, &v13);
        WindowsDeleteString(string);
        string = 0;
        TileNotificationManager::GetTileID(a2, &string);
        v6 = string;
        *((_BYTE *)a2 + 118) = 1;
        StringRawBuffer = WindowsGetStringRawBuffer(v6, 0);
        v10[0] = WindowsGetStringRawBuffer(v13, 0);
        NotificationTelemetry::ProcessingDeferred<unsigned short const *,unsigned short const *>(v10, &StringRawBuffer);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v13);
      }
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA68,
      (unsigned int)"shellcommon\\shell\\tiles\\sharedmodel\\notificationqueuemanager\\lib\\notificationqueuemanager.cpp",
      (const char *)(unsigned int)NotificationId,
      (int)v8);
    v5 = 0;
  }
  WindowsDeleteString(v8);
  return v5;
}

```

## disassembly

```asm
0x1801d98b0  mov     [rsp-8+arg_0], rbx
0x1801d98b5  mov     [rsp-8+arg_8], rdi
0x1801d98ba  push    rbp
0x1801d98bb  mov     rbp, rsp
0x1801d98be  sub     rsp, 40h
0x1801d98c2  mov     rbx, rcx
0x1801d98c5  mov     [rbp+var_20], 0
0x1801d98cd  xor     ecx, ecx; string
0x1801d98cf  mov     rdi, rdx
0x1801d98d2  call    cs:__imp_WindowsDeleteString
0x1801d98d8  lea     rdx, [rbp+var_20]; HSTRING *
0x1801d98dc  mov     [rbp+var_20], 0
0x1801d98e4  mov     rcx, rdi; this
0x1801d98e7  call    ?GetNotificationId@TileNotificationManager@@UEAAJPEAPEAUHSTRING__@@@Z; TileNotificationManager::GetNotificationId(HSTRING__ * *)
0x1801d98ec  test    eax, eax
0x1801d98ee  jns     short loc_1801D990F
0x1801d98f0  mov     rcx, [rbp+8]; this
0x1801d98f4  lea     r8, aShellcommonShe_201; "shellcommon\\shell\\tiles\\sharedmodel"...
0x1801d98fb  mov     r9d, eax; char *
0x1801d98fe  mov     edx, 0A68h; void *
0x1801d9903  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801d9908  xor     ebx, ebx
0x1801d990a  jmp     loc_1801D99CF
0x1801d990f  cmp     byte ptr [rbx+0E8h], 0
0x1801d9916  jnz     loc_1801D99CD
0x1801d991c  lea     rcx, [rbx+60h]
0x1801d9920  lea     rdx, [rbp+var_20]
0x1801d9924  call    ?count@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@_NUhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@_N@std@@@std@@$0A@@std@@@std@@QEBA_KAEBVHString@Wrappers@WRL@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,bool,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,bool>>,0>>::count(Microsoft::WRL::Wrappers::HString const &)
0x1801d9929  test    rax, rax
0x1801d992c  jnz     loc_1801D99CD
0x1801d9932  mov     bl, 1
0x1801d9934  cmp     [rdi+76h], al
0x1801d9937  jnz     loc_1801D99CF
0x1801d993d  xor     ecx, ecx; string
0x1801d993f  mov     [rbp+arg_18], rax
0x1801d9943  mov     [rbp+string], rax
0x1801d9947  call    cs:__imp_WindowsDeleteString
0x1801d994d  lea     rdx, [rbp+arg_18]; HSTRING *
0x1801d9951  mov     [rbp+arg_18], 0
0x1801d9959  mov     rcx, rdi; this
0x1801d995c  call    ?GetApplicationUserModelId@TileNotificationManager@@UEAAJPEAPEAUHSTRING__@@@Z; TileNotificationManager::GetApplicationUserModelId(HSTRING__ * *)
0x1801d9961  mov     rcx, [rbp+string]; string
0x1801d9965  call    cs:__imp_WindowsDeleteString
0x1801d996b  lea     rdx, [rbp+string]; HSTRING *
0x1801d996f  mov     [rbp+string], 0
0x1801d9977  mov     rcx, rdi; this
0x1801d997a  call    ?GetTileID@TileNotificationManager@@UEAAJPEAPEAUHSTRING__@@@Z; TileNotificationManager::GetTileID(HSTRING__ * *)
0x1801d997f  mov     rcx, [rbp+string]; string
0x1801d9983  xor     edx, edx; length
0x1801d9985  mov     [rdi+76h], bl
0x1801d9988  call    cs:__imp_WindowsGetStringRawBuffer
0x1801d998e  mov     rcx, [rbp+arg_18]; string
0x1801d9992  xor     edx, edx; length
0x1801d9994  mov     [rbp+var_18], rax
0x1801d9998  call    cs:__imp_WindowsGetStringRawBuffer
0x1801d999e  lea     rdx, [rbp+var_18]
0x1801d99a2  mov     [rbp+var_10], rax
0x1801d99a6  lea     rcx, [rbp+var_10]
0x1801d99aa  call    ??$ProcessingDeferred@PEBGPEBG@NotificationTelemetry@@SAX$$QEAPEBG0@Z; NotificationTelemetry::ProcessingDeferred<ushort const *,ushort const *>(ushort const * &&,ushort const * &&)
0x1801d99af  mov     rcx, [rbp+string]; string
0x1801d99b3  call    cs:__imp_WindowsDeleteString
0x1801d99b9  mov     rcx, [rbp+arg_18]; string
0x1801d99bd  mov     [rbp+string], 0
0x1801d99c5  call    cs:__imp_WindowsDeleteString
0x1801d99cb  jmp     short loc_1801D99CF
0x1801d99cd  xor     bl, bl
0x1801d99cf  mov     rcx, [rbp+var_20]; string
0x1801d99d3  call    cs:__imp_WindowsDeleteString
0x1801d99d9  mov     rdi, [rsp+40h+arg_8]
0x1801d99de  mov     al, bl
0x1801d99e0  mov     rbx, [rsp+40h+arg_0]
0x1801d99e5  add     rsp, 40h
0x1801d99e9  pop     rbp
0x1801d99ea  retn
```
