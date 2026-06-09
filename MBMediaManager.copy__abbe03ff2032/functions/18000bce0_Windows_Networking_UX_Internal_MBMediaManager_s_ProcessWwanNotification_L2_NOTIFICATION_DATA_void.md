# Windows::Networking::UX::Internal::MBMediaManager::s_ProcessWwanNotification(_L2_NOTIFICATION_DATA *,void *)

- ea: `0x18000bce0`
- end: `0x18000bdcb`
- name: `?s_ProcessWwanNotification@MBMediaManager@Internal@UX@Networking@Windows@@SAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z`
- size: `235`
- prototype: `void __fastcall(struct _L2_NOTIFICATION_DATA *, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000bce0`
- `0x18000bde0`
- `0x18000fde0`
- `0x18001bdb8`
- `0x18001cb10`
- `0x18002d20c`
- `0x180059010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x18000bd51`
- `SHCORE!SHTaskPoolQueueTask` at `0x18000bd51`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Networking::UX::Internal::MBMediaManager::s_ProcessWwanNotification(
        struct _L2_NOTIFICATION_DATA *a1,
        _DWORD *a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  unsigned int v7; // ebp
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  int v10; // edi
  int v11; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( a1 && a2 )
  {
    v7 = a2[24];
    v8 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v8;
    if ( v8 )
    {
      Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(v8);
      v9[2] = a2;
      v9[3] = a1;
      *v9 = &off_18005C9E0;
    }
    v10 = SHTaskPoolQueueTask(0, 34, v7, 0, v9, 0);
    if ( v9 )
      (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17F,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbmediamanager.cpp",
        (const char *)(unsigned int)v10,
        v11);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x182,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbmediamanager.cpp",
        (const char *)(unsigned int)v10,
        a5);
    }
  }
  else
  {
    MBSettingUXLogging::Warn(
      "Windows::Networking::UX::Internal::MBMediaManager::s_ProcessWwanNotification",
      362,
      "Notification payload or context contains nullptr. Ignore bad notifications");
  }
}

```

## disassembly

```asm
0x18000bce0  push    rbx
0x18000bce2  push    rbp
0x18000bce3  push    rsi
0x18000bce4  push    rdi
0x18000bce5  sub     rsp, 38h
0x18000bce9  mov     rsi, rdx
0x18000bcec  mov     rdi, rcx
0x18000bcef  test    rcx, rcx
0x18000bcf2  jz      short loc_18000BCF9
0x18000bcf4  test    rdx, rdx
0x18000bcf7  jnz     short loc_18000BD1A
0x18000bcf9  lea     r8, aNotificationPa; "Notification payload or context contain"...
0x18000bd00  mov     edx, 16Ah; unsigned int
0x18000bd05  lea     rcx, aWindowsNetwork_217; "Windows::Networking::UX::Internal::MBMe"...
0x18000bd0c  call    ?Warn@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Warn(char const *,ulong,char const *,...)
0x18000bd11  add     rsp, 38h
0x18000bd15  pop     rdi
0x18000bd16  pop     rsi
0x18000bd17  pop     rbp
0x18000bd18  pop     rbx
0x18000bd19  retn
0x18000bd1a  mov     ebp, [rdx+60h]
0x18000bd1d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000bd24  mov     ecx, 20h ; ' '; unsigned __int64
0x18000bd29  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000bd2e  mov     rbx, rax
0x18000bd31  test    rax, rax
0x18000bd34  jnz     short loc_18000BDAC
0x18000bd36  mov     [rsp+58h+var_30], 0
0x18000bd3f  mov     qword ptr [rsp+58h+var_38], rbx; int
0x18000bd44  xor     r9d, r9d
0x18000bd47  mov     r8d, ebp
0x18000bd4a  mov     edx, 22h ; '"'
0x18000bd4f  xor     ecx, ecx
0x18000bd51  call    cs:__imp_SHTaskPoolQueueTask
0x18000bd57  mov     edi, eax
0x18000bd59  test    rbx, rbx
0x18000bd5c  jz      short loc_18000BD6E
0x18000bd5e  mov     rcx, [rbx]
0x18000bd61  mov     rax, [rcx+10h]
0x18000bd65  mov     rcx, rbx
0x18000bd68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd6d  nop
0x18000bd6e  test    edi, edi
0x18000bd70  jns     short loc_18000BD11
0x18000bd72  mov     rcx, [rsp+58h]; this
0x18000bd77  mov     r9d, edi; char *
0x18000bd7a  lea     r8, aOnecoreuapNetU_15; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18000bd81  mov     edx, 17Fh; void *
0x18000bd86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bd8b  mov     rcx, [rsp+58h]; this
0x18000bd90  mov     r9d, edi; char *
0x18000bd93  lea     r8, aOnecoreuapNetU_15; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18000bd9a  mov     edx, 182h; void *
0x18000bd9f  add     rsp, 38h
0x18000bda3  pop     rdi
0x18000bda4  pop     rsi
0x18000bda5  pop     rbp
0x18000bda6  pop     rbx
0x18000bda7  jmp     ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000bdac  mov     rcx, rbx
0x18000bdaf  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(void)
0x18000bdb4  mov     [rbx+10h], rsi
0x18000bdb8  mov     [rbx+18h], rdi
0x18000bdbc  lea     rax, off_18005C9E0
0x18000bdc3  mov     [rbx], rax
0x18000bdc6  jmp     loc_18000BD36
```
