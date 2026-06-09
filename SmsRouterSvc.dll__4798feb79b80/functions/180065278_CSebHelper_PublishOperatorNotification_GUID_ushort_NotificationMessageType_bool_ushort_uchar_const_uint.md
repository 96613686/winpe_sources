# CSebHelper::PublishOperatorNotification(_GUID,ushort *,NotificationMessageType,bool,ushort *,uchar const *,uint)

- ea: `0x180065278`
- end: `0x1800654c1`
- name: `?PublishOperatorNotification@CSebHelper@@SAJU_GUID@@PEAGW4NotificationMessageType@@_N1PEBEI@Z`
- size: `585`
- prototype: `static int __high(struct _GUID, unsigned __int16 *, enum NotificationMessageType, bool, unsigned __int16 *, const unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18004c7b4`
- `0x18004cf34`

## callees

- `0x180003a60`
- `0x180004980`
- `0x180004998`
- `0x180051420`
- `0x180051628`
- `0x180065278`
- `0x1800656a8`
- `0x1800696fc`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800652f2`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800652f2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800653d1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180065402`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800653d1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180065402`
- `OLEAUT32!__imp_SysStringLen` at `0x1800652fe`
- `OLEAUT32!__imp_SysStringLen` at `0x1800652fe`

## string_xrefs

- `0x1800653db`: `CSebHelper::PublishOperatorNotification error copying RuleId.`
- `0x180065462`: `CSebHelper::PublishOperatorNotification error copying message.`

## pseudocode

```c
__int64 __fastcall CSebHelper::PublishOperatorNotification(
        struct _GUID *a1,
        OLECHAR *a2,
        int a3,
        char a4,
        wchar_t *Source,
        void *a6,
        unsigned int Size)
{
  size_t v10; // rdi
  UINT v11; // eax
  UINT v12; // r15d
  int WnfStateName; // ebx
  __int64 v14; // rdx
  int v15; // eax
  int v16; // ecx
  _WNF_STATE_NAME v19; // [rsp+48h] [rbp-B8h] BYREF
  void *Src; // [rsp+50h] [rbp-B0h]
  struct _GUID v21; // [rsp+60h] [rbp-A0h] BYREF
  struct _GUID v22; // [rsp+70h] [rbp-90h] BYREF
  __int128 v23; // [rsp+80h] [rbp-80h] BYREF
  int v24; // [rsp+90h] [rbp-70h]
  struct _GUID v25; // [rsp+94h] [rbp-6Ch]
  char v26; // [rsp+A4h] [rbp-5Ch]
  BOOL v27; // [rsp+A8h] [rbp-58h]
  unsigned int v28; // [rsp+ACh] [rbp-54h]
  char v29[200]; // [rsp+B0h] [rbp-50h] BYREF
  int v30; // [rsp+178h] [rbp+78h]
  char v31[512]; // [rsp+17Ch] [rbp+7Ch] BYREF
  UINT v32; // [rsp+37Ch] [rbp+27Ch]
  char v33[352]; // [rsp+380h] [rbp+280h] BYREF

  Src = a6;
  LogSmsRouterInfo("CSebHelper::PublishOperatorNotification", 0x6Bu, "PublishOperatorNotification Enter");
  v10 = 0;
  if ( Source )
    v10 = wcsnlen(Source, 0x104u);
  v11 = SysStringLen(a2);
  v12 = v11;
  if ( v10 >= 0x104 || v11 > 0xA0 || Size > 0xC8 )
  {
    WnfStateName = -2147024809;
  }
  else
  {
    v21 = *a1;
    v19 = 0;
    v22 = 0;
    WnfStateName = CSebHelper::_GetWnfStateName(&v21, &v19, &v22);
    if ( WnfStateName >= 0 )
    {
      memset_0(&v23, 0, 0x458u);
      v24 = a3;
      v23 = xmmword_18007C318;
      v26 = 1;
      v32 = v12;
      v27 = a4 != 0;
      v25 = v22;
      v28 = Size;
      v30 = v10;
      memcpy_0(v29, Src, Size);
      if ( v10 && (unsigned int)_o_wcscpy_s(v31, 255, Source) )
        LogSmsRouterInfo(
          "CSebHelper::PublishOperatorNotification",
          0x9Au,
          "CSebHelper::PublishOperatorNotification error copying RuleId.");
      if ( (unsigned int)_o_wcscpy_s(v33, 161, a2) )
      {
        LogSmsRouterInfo(
          "CSebHelper::PublishOperatorNotification",
          0xAFu,
          "CSebHelper::PublishOperatorNotification error copying message.");
      }
      else
      {
        LogSmsRouterInfo(
          "CSebHelper::PublishOperatorNotification",
          0xA0u,
          "SmsRouter publishing operator message to SEB");
        v15 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))PubSebEdgeEventSyncInternal)(
                v19,
                v14,
                &v23,
                1112);
        v16 = v15 | 0x10000000;
        if ( v15 >= 0 )
          v16 = WnfStateName;
        WnfStateName = v16;
        LogSmsRouterError(
          "CSebHelper::PublishOperatorNotification",
          0xABu,
          v16,
          "CSebHelper::PublishOperatorNotification PubSebEdgeEventSync returned error");
      }
    }
  }
  LogSmsRouterInfo(
    "CSebHelper::PublishOperatorNotification",
    0xB4u,
    "PublishOperatorNotification Exit hr = 0x%x",
    WnfStateName);
  return (unsigned int)WnfStateName;
}

```

## disassembly

```asm
0x180065278  mov     [rsp-8+arg_18], rbx
0x18006527d  push    rbp
0x18006527e  push    rsi
0x18006527f  push    rdi
0x180065280  push    r12
0x180065282  push    r13
0x180065284  push    r14
0x180065286  push    r15
0x180065288  lea     rbp, [rsp-3F0h]
0x180065290  sub     rsp, 4F0h
0x180065297  mov     rax, cs:__security_cookie
0x18006529e  xor     rax, rsp
0x1800652a1  mov     [rbp+420h+var_40], rax
0x1800652a8  mov     rax, [rbp+420h+arg_28]
0x1800652af  mov     r12, rdx
0x1800652b2  mov     r14, [rbp+420h+Source]
0x1800652b9  mov     rbx, rcx
0x1800652bc  mov     [rsp+520h+var_4E0], r8d
0x1800652c1  lea     rcx, aCsebhelperPubl_0; "CSebHelper::PublishOperatorNotification"
0x1800652c8  lea     r8, aPublishoperato; "PublishOperatorNotification Enter"
0x1800652cf  mov     [rsp+520h+Src], rax
0x1800652d4  mov     edx, 6Bh ; 'k'; unsigned int
0x1800652d9  mov     r13b, r9b
0x1800652dc  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x1800652e1  xor     edi, edi
0x1800652e3  mov     esi, 104h
0x1800652e8  test    r14, r14
0x1800652eb  jz      short loc_1800652FB
0x1800652ed  mov     edx, esi; MaxCount
0x1800652ef  mov     rcx, r14; Source
0x1800652f2  call    cs:__imp_wcsnlen
0x1800652f8  mov     rdi, rax
0x1800652fb  mov     rcx, r12; pbstr
0x1800652fe  call    cs:__imp_SysStringLen
0x180065304  mov     r15d, eax
0x180065307  cmp     rdi, rsi
0x18006530a  jnb     loc_180065475
0x180065310  cmp     eax, 0A0h
0x180065315  ja      loc_180065475
0x18006531b  mov     esi, dword ptr [rbp+420h+Size]
0x180065321  cmp     esi, 0C8h
0x180065327  ja      loc_180065475
0x18006532d  movaps  xmm1, xmmword ptr [rbx]
0x180065330  lea     r8, [rsp+520h+var_4B0]; struct _GUID *
0x180065335  xorps   xmm0, xmm0
0x180065338  movdqa  xmmword ptr [rsp+520h+var_4C0.Data1], xmm1
0x18006533e  lea     rdx, [rsp+520h+var_4D8]; struct _WNF_STATE_NAME *
0x180065343  mov     qword ptr [rsp+520h+var_4D8.Data], 0
0x18006534c  lea     rcx, [rsp+520h+var_4C0]; struct _GUID
0x180065351  movups  xmmword ptr [rsp+520h+var_4B0.Data1], xmm0
0x180065356  call    ?_GetWnfStateName@CSebHelper@@CAJU_GUID@@PEAU_WNF_STATE_NAME@@PEAU2@@Z; CSebHelper::_GetWnfStateName(_GUID,_WNF_STATE_NAME *,_GUID *)
0x18006535b  mov     ebx, eax
0x18006535d  test    eax, eax
0x18006535f  js      loc_18006547A
0x180065365  xor     edx, edx; Val
0x180065367  lea     rcx, [rbp+420h+var_4A0]; void *
0x18006536b  mov     r8d, 458h; Size
0x180065371  call    memset_0
0x180065376  movups  xmm0, cs:xmmword_18007C318
0x18006537d  mov     eax, [rsp+520h+var_4E0]
0x180065381  lea     rcx, [rbp+420h+var_470]; void *
0x180065385  mov     rdx, [rsp+520h+Src]; Src
0x18006538a  mov     r8d, esi; Size
0x18006538d  mov     [rbp+420h+var_490], eax
0x180065390  xor     eax, eax
0x180065392  movdqu  [rbp+420h+var_4A0], xmm0
0x180065397  test    r13b, r13b
0x18006539a  mov     [rbp+420h+var_47C], 1
0x18006539e  movups  xmm0, xmmword ptr [rsp+520h+var_4B0.Data1]
0x1800653a3  setnz   al
0x1800653a6  mov     [rbp+420h+var_1A4], r15d
0x1800653ad  mov     [rbp+420h+var_478], eax
0x1800653b0  movdqu  [rbp+420h+var_48C], xmm0
0x1800653b5  mov     [rbp+420h+var_474], esi
0x1800653b8  mov     [rbp+420h+var_3A8], edi
0x1800653bb  call    memcpy_0
0x1800653c0  test    rdi, rdi
0x1800653c3  jz      short loc_1800653F3
0x1800653c5  mov     r8, r14
0x1800653c8  lea     rcx, [rbp+420h+var_3A4]
0x1800653cc  mov     edx, 0FFh
0x1800653d1  call    cs:__imp__o_wcscpy_s
0x1800653d7  test    eax, eax
0x1800653d9  jz      short loc_1800653F3
0x1800653db  lea     r8, aCsebhelperPubl_1; "CSebHelper::PublishOperatorNotification"...
0x1800653e2  mov     edx, 9Ah; unsigned int
0x1800653e7  lea     rcx, aCsebhelperPubl_0; "CSebHelper::PublishOperatorNotification"
0x1800653ee  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x1800653f3  mov     r8, r12
0x1800653f6  lea     rcx, [rbp+420h+var_1A0]
0x1800653fd  mov     edx, 0A1h
0x180065402  call    cs:__imp__o_wcscpy_s
0x180065408  lea     rcx, aCsebhelperPubl_0; "CSebHelper::PublishOperatorNotification"
0x18006540f  test    eax, eax
0x180065411  jnz     short loc_180065462
0x180065413  lea     r8, aSmsrouterPubli; "SmsRouter publishing operator message t"...
0x18006541a  mov     edx, 0A0h; unsigned int
0x18006541f  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180065424  mov     rcx, qword ptr [rsp+520h+var_4D8.Data]
0x180065429  lea     r8, [rbp+420h+var_4A0]
0x18006542d  mov     r9d, 458h
0x180065433  call    PubSebEdgeEventSyncInternal
0x180065438  mov     ecx, eax
0x18006543a  lea     r9, aCsebhelperPubl_3; "CSebHelper::PublishOperatorNotification"...
0x180065441  bts     ecx, 1Ch
0x180065445  mov     edx, 0ABh; unsigned int
0x18006544a  test    eax, eax
0x18006544c  cmovns  ecx, ebx
0x18006544f  mov     ebx, ecx
0x180065451  mov     r8d, ecx; int
0x180065454  lea     rcx, aCsebhelperPubl_0; "CSebHelper::PublishOperatorNotification"
0x18006545b  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180065460  jmp     short loc_18006547A
0x180065462  lea     r8, aCsebhelperPubl; "CSebHelper::PublishOperatorNotification"...
0x180065469  mov     edx, 0AFh; unsigned int
0x18006546e  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180065473  jmp     short loc_18006547A
0x180065475  mov     ebx, 80070057h
0x18006547a  mov     r9d, ebx
0x18006547d  lea     r8, aPublishoperato_0; "PublishOperatorNotification Exit hr = 0"...
0x180065484  mov     edx, 0B4h; unsigned int
0x180065489  lea     rcx, aCsebhelperPubl_0; "CSebHelper::PublishOperatorNotification"
0x180065490  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180065495  mov     eax, ebx
0x180065497  mov     rcx, [rbp+420h+var_40]
0x18006549e  xor     rcx, rsp; StackCookie
0x1800654a1  call    __security_check_cookie
0x1800654a6  mov     rbx, [rsp+520h+arg_18]
0x1800654ae  add     rsp, 4F0h
0x1800654b5  pop     r15
0x1800654b7  pop     r14
0x1800654b9  pop     r13
0x1800654bb  pop     r12
0x1800654bd  pop     rdi
0x1800654be  pop     rsi
0x1800654bf  pop     rbp
0x1800654c0  retn
```
