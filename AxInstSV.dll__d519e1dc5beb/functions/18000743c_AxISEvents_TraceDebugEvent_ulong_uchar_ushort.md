# AxISEvents::TraceDebugEvent(ulong,uchar,ushort *)

- ea: `0x18000743c`
- end: `0x18000750e`
- name: `?TraceDebugEvent@AxISEvents@@QEAAHKEPEAG@Z`
- size: `210`
- prototype: `__int64 __fastcall(AxISEvents *__hidden this, unsigned int, unsigned __int8, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000725c`

## callees

- `0x180001720`
- `0x18000743c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800074ea`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800074ea`

## pseudocode

```c
_BOOL8 __fastcall AxISEvents::TraceDebugEvent(AxISEvents *this, int a2, char a3, unsigned __int16 *a4)
{
  REGHANDLE v4; // rcx
  ULONG v5; // r10d
  __int64 v6; // rax
  int v7; // edx
  int v8; // edx
  int v9; // edx
  const EVENT_DESCRIPTOR *v10; // rax
  const EVENT_DESCRIPTOR *v11; // rdx
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-28h] BYREF

  v4 = *((_QWORD *)this + 4);
  v5 = 0;
  if ( v4 )
  {
    UserData.Ptr = (ULONGLONG)a4;
    v6 = -1;
    do
      ++v6;
    while ( a4[v6] );
    UserData.Reserved = 0;
    UserData.Size = 2 * v6 + 2;
    v7 = a2 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 2;
        if ( v9 )
        {
          if ( v9 != 4 )
            return v5 == 0;
          v10 = &AXIS_SERV_DBG_INFO_GENERAL;
          v11 = (const EVENT_DESCRIPTOR *)&AXIS_SERV_DBG_ERR_GENERAL;
        }
        else
        {
          v10 = (const EVENT_DESCRIPTOR *)&AXIS_SERV_DBG_INFO_URL_CACHE;
          v11 = (const EVENT_DESCRIPTOR *)&AXIS_SERV_DBG_ERR_URL_CACHE;
        }
      }
      else
      {
        v10 = (const EVENT_DESCRIPTOR *)&AXIS_SERV_DBG_INFO_DOWNLOAD;
        v11 = (const EVENT_DESCRIPTOR *)&AXIS_SERV_DBG_ERR_DOWNLOAD;
      }
    }
    else
    {
      v10 = (const EVENT_DESCRIPTOR *)&AXIS_SERV_DBG_INFO_ZONE_POLICY;
      v11 = (const EVENT_DESCRIPTOR *)&AXIS_SERV_DBG_ERR_ZONE_POLICY;
    }
    if ( a3 != 2 )
      v11 = v10;
    v5 = EventWrite(v4, v11, 1u, &UserData);
  }
  return v5 == 0;
}

```

## disassembly

```asm
0x18000743c  push    rbx
0x18000743e  sub     rsp, 40h
0x180007442  mov     rax, cs:__security_cookie
0x180007449  xor     rax, rsp
0x18000744c  mov     [rsp+48h+var_18], rax
0x180007451  mov     rcx, [rcx+20h]; RegHandle
0x180007455  xor     ebx, ebx
0x180007457  mov     r10d, ebx
0x18000745a  test    rcx, rcx
0x18000745d  jz      loc_1800074F3
0x180007463  mov     [rsp+48h+UserData.Ptr], r9
0x180007468  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000746c  inc     rax
0x18000746f  cmp     [r9+rax*2], bx
0x180007474  jnz     short loc_18000746C
0x180007476  mov     dword ptr [rsp+48h+UserData.0Ch], ebx
0x18000747a  lea     eax, ds:2[rax*2]
0x180007481  mov     [rsp+48h+UserData.Size], eax
0x180007485  sub     edx, 1
0x180007488  jz      short loc_1800074C9
0x18000748a  sub     edx, 1
0x18000748d  jz      short loc_1800074B9
0x18000748f  sub     edx, 2
0x180007492  jz      short loc_1800074A9
0x180007494  cmp     edx, 4
0x180007497  jnz     short loc_1800074F3
0x180007499  lea     rax, AXIS_SERV_DBG_INFO_GENERAL
0x1800074a0  lea     rdx, AXIS_SERV_DBG_ERR_GENERAL
0x1800074a7  jmp     short loc_1800074D7
0x1800074a9  lea     rax, AXIS_SERV_DBG_INFO_URL_CACHE
0x1800074b0  lea     rdx, AXIS_SERV_DBG_ERR_URL_CACHE
0x1800074b7  jmp     short loc_1800074D7
0x1800074b9  lea     rax, AXIS_SERV_DBG_INFO_DOWNLOAD
0x1800074c0  lea     rdx, AXIS_SERV_DBG_ERR_DOWNLOAD
0x1800074c7  jmp     short loc_1800074D7
0x1800074c9  lea     rax, AXIS_SERV_DBG_INFO_ZONE_POLICY
0x1800074d0  lea     rdx, AXIS_SERV_DBG_ERR_ZONE_POLICY
0x1800074d7  cmp     r8b, 2
0x1800074db  lea     r9, [rsp+48h+UserData]; UserData
0x1800074e0  mov     r8d, 1; UserDataCount
0x1800074e6  cmovnz  rdx, rax; EventDescriptor
0x1800074ea  call    cs:__imp_EventWrite
0x1800074f0  mov     r10d, eax
0x1800074f3  test    r10d, r10d
0x1800074f6  mov     eax, ebx
0x1800074f8  setz    al
0x1800074fb  mov     rcx, [rsp+48h+var_18]
0x180007500  xor     rcx, rsp; StackCookie
0x180007503  call    __security_check_cookie
0x180007508  add     rsp, 40h
0x18000750c  pop     rbx
0x18000750d  retn
```
