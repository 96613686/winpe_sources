# Uev::NotificationListener::Stop(void)

- ea: `0x140019f8c`
- end: `0x14001a05d`
- name: `?Stop@NotificationListener@Uev@@QEAAXXZ`
- size: `209`
- prototype: `void __fastcall(Uev::NotificationListener *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x14000b8cc`

## callees

- `0x14000ac28`
- `0x14000ac58`
- `0x14000ac88`
- `0x14000acc4`
- `0x140014998`
- `0x1400191ec`
- `0x140019f8c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140019fb7`
- `KERNEL32!CloseHandle` at `0x140019fb7`
- `KERNEL32!Sleep` at `0x140019fd1`
- `KERNEL32!Sleep` at `0x140019fd1`

## string_xrefs

- `0x140019ff6`: `AgentService.FilterConnection::Close: Entry`
- `0x14001a029`: `AgentService.FilterConnection::Close: Exit, retStatus = 0x%X`
- `0x140019f9d`: `AgentService.NotificationListener::Stop: Entry`
- `0x140019fea`: `AgentService.NotificationListener::Stop: Timed out waiting for threads to exit`
- `0x14001a03b`: `AgentService.NotificationListener::Stop: Filter connection close failed, status = 0x%X`
- `0x14001a047`: `AgentService.NotificationListener::Stop: Exit`

## pseudocode

```c
void __fastcall Uev::NotificationListener::Stop(Uev::NotificationListener *this, __int64 a2)
{
  _QWORD *v2; // rbx
  void *v3; // rcx
  unsigned int v4; // edi
  int v5; // ebx
  __int64 v6; // rdx

  v2 = pCreateProcNotificationListener;
  DbgTrace<4>(L"AgentService.NotificationListener::Stop: Entry", a2);
  if ( *((_BYTE *)v2 + 20) )
  {
    v3 = (void *)v2[1];
    *((_BYTE *)v2 + 20) = 0;
    CloseHandle(v3);
    v4 = 0;
    v2[1] = 0;
    if ( *((_DWORD *)v2 + 12) )
    {
      while ( 1 )
      {
        Sleep(0x64u);
        v4 += 100;
        if ( v4 >= *((_DWORD *)v2 + 36) )
          break;
        if ( !*((_DWORD *)v2 + 12) )
          goto LABEL_7;
      }
      DbgTrace<2>(L"AgentService.NotificationListener::Stop: Timed out waiting for threads to exit");
    }
  }
LABEL_7:
  DbgTrace<5>(L"AgentService.FilterConnection::Close: Entry");
  if ( (unsigned __int64)(v2[19] - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v5 = -2147022646;
  }
  else
  {
    Uev::SmartHandle<void *,&void Uev::CloseHandleWrapper(void *),-1>::Close(v2 + 19);
    v5 = 0;
  }
  DbgTraceFrmt<5,long>((wchar_t *)L"AgentService.FilterConnection::Close: Exit, retStatus = 0x%X");
  if ( v5 < 0 )
    DbgTraceFrmtErr<long>((wchar_t *)L"AgentService.NotificationListener::Stop: Filter connection close failed, status = 0x%X");
  DbgTrace<4>(L"AgentService.NotificationListener::Stop: Exit", v6);
}

```

## disassembly

```asm
0x140019f8c  mov     [rsp+arg_0], rbx
0x140019f91  push    rdi
0x140019f92  sub     rsp, 20h
0x140019f96  mov     rbx, cs:?pCreateProcNotificationListener@@3PEAVCreateProcNotificationListener@Uev@@EA; Uev::CreateProcNotificationListener * pCreateProcNotificationListener
0x140019f9d  lea     rcx, aAgentserviceNo_7; "AgentService.NotificationListener::Stop"...
0x140019fa4  call    ??$DbgTrace@$03@@YAXPEB_W@Z; DbgTrace<4>(wchar_t const *)
0x140019fa9  cmp     byte ptr [rbx+14h], 0
0x140019fad  jz      short loc_140019FF6
0x140019faf  mov     rcx, [rbx+8]; hObject
0x140019fb3  mov     byte ptr [rbx+14h], 0
0x140019fb7  call    cs:__imp_CloseHandle
0x140019fbd  xor     edi, edi
0x140019fbf  mov     qword ptr [rbx+8], 0
0x140019fc7  cmp     [rbx+30h], edi
0x140019fca  jz      short loc_140019FF6
0x140019fcc  mov     ecx, 64h ; 'd'; dwMilliseconds
0x140019fd1  call    cs:__imp_Sleep
0x140019fd7  add     edi, 64h ; 'd'
0x140019fda  cmp     edi, [rbx+90h]
0x140019fe0  jnb     short loc_140019FEA
0x140019fe2  cmp     dword ptr [rbx+30h], 0
0x140019fe6  jnz     short loc_140019FCC
0x140019fe8  jmp     short loc_140019FF6
0x140019fea  lea     rcx, aAgentserviceNo_6; "AgentService.NotificationListener::Stop"...
0x140019ff1  call    ??$DbgTrace@$01@@YAXPEB_W@Z; DbgTrace<2>(wchar_t const *)
0x140019ff6  lea     rcx, aAgentserviceFi_9; "AgentService.FilterConnection::Close: E"...
0x140019ffd  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x14001a002  mov     rax, [rbx+98h]
0x14001a009  dec     rax
0x14001a00c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001a010  ja      short loc_14001A022
0x14001a012  lea     rcx, [rbx+98h]
0x14001a019  call    ?Close@?$SmartHandle@PEAX$1?CloseHandleWrapper@Uev@@YAXPEAX@Z$0?0@Uev@@QEAAXXZ; Uev::SmartHandle<void *,&Uev::CloseHandleWrapper(void *),-1>::Close(void)
0x14001a01e  xor     ebx, ebx
0x14001a020  jmp     short loc_14001A027
0x14001a022  mov     ebx, 800708CAh
0x14001a027  mov     edx, ebx
0x14001a029  lea     rcx, aAgentserviceFi_7; "AgentService.FilterConnection::Close: E"...
0x14001a030  call    ??$DbgTraceFrmt@$04J@@YAXPEB_WJ@Z; DbgTraceFrmt<5,long>(wchar_t const *,long)
0x14001a035  test    ebx, ebx
0x14001a037  jns     short loc_14001A047
0x14001a039  mov     edx, ebx
0x14001a03b  lea     rcx, aAgentserviceNo_15; "AgentService.NotificationListener::Stop"...
0x14001a042  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x14001a047  lea     rcx, aAgentserviceNo_1; "AgentService.NotificationListener::Stop"...
0x14001a04e  mov     rbx, [rsp+28h+arg_0]
0x14001a053  add     rsp, 20h
0x14001a057  pop     rdi
0x14001a058  jmp     ??$DbgTrace@$03@@YAXPEB_W@Z; DbgTrace<4>(wchar_t const *)
```
