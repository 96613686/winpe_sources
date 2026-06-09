# CEtwLogHelper::StopTraceSession(ushort const *)

- ea: `0x180013e4c`
- end: `0x180013fde`
- name: `?StopTraceSession@CEtwLogHelper@@SAJPEBG@Z`
- size: `402`
- prototype: `__int64 __fastcall(LPCWSTR InstanceName)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ea40`

## callees

- `0x1800011a4`
- `0x180001b60`
- `0x180013820`
- `0x18001395c`
- `0x180013a4c`
- `0x180013e4c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013faf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013faf`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180013ee6`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180013ee6`

## pseudocode

```c
__int64 __fastcall CEtwLogHelper::StopTraceSession(
        unsigned __int16 *InstanceName,
        __int64 a2,
        unsigned __int16 *a3,
        __int64 a4)
{
  WCHAR *v4; // rsi
  PEVENT_TRACE_PROPERTIES v5; // rdi
  int TraceSessionStatus; // ebx
  int v7; // eax
  signed int v8; // eax
  unsigned __int16 *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  int v13; // [rsp+30h] [rbp-D0h] BYREF
  PEVENT_TRACE_PROPERTIES Properties; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v15[1032]; // [rsp+40h] [rbp-C0h] BYREF

  v4 = InstanceName;
  v13 = 0;
  v5 = 0;
  Properties = 0;
  if ( InstanceName )
  {
    TraceSessionStatus = CEtwLogHelper::GetTraceSessionStatus(InstanceName, &v13);
    if ( TraceSessionStatus >= 0 )
    {
      if ( v13 )
      {
        v7 = CEtwLogHelper::CreateSessionProperty(&Properties);
        v5 = Properties;
        TraceSessionStatus = v7;
        if ( v7 >= 0 )
        {
          v8 = ControlTraceW(0, v4, Properties, 1u);
          TraceSessionStatus = v8;
          if ( v8 )
          {
            if ( v8 > 0 )
              TraceSessionStatus = (unsigned __int16)v8 | 0x80070000;
          }
          else
          {
            a3 = v15;
            v9 = (unsigned __int16 *)((char *)v5 + v5->LogFileNameOffset);
            v10 = 2147483646;
            v11 = 1025;
            do
            {
              if ( !v10 )
                break;
              a4 = *v9;
              if ( !(_WORD)a4 )
                break;
              *a3 = a4;
              ++v9;
              ++a3;
              --v10;
              --v11;
            }
            while ( v11 );
            InstanceName = a3 - 1;
            TraceSessionStatus = v11 == 0 ? 0x8007007A : 0;
            if ( v11 )
              InstanceName = a3;
            *InstanceName = 0;
            if ( v11 )
              TraceSessionStatus = CEtwLogHelper::CreateDecodedEtlFile(v15, v11, (__int64)a3, a4);
          }
        }
      }
      else
      {
        TraceSessionStatus = 0;
      }
    }
  }
  else
  {
    TraceSessionStatus = -2147024809;
  }
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v13 = TraceSessionStatus;
    if ( !v4 )
      v4 = (WCHAR *)&String2;
    Properties = (PEVENT_TRACE_PROPERTIES)v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)InstanceName,
      (__int64)word_18004015A,
      (__int64)a3,
      a4,
      (const WCHAR **)&Properties,
      (__int64)&v13);
  }
  if ( v5 )
    CoTaskMemFree(v5);
  return (unsigned int)TraceSessionStatus;
}

```

## disassembly

```asm
0x180013e4c  mov     [rsp-8+arg_8], rbx
0x180013e51  mov     [rsp-8+arg_10], rsi
0x180013e56  push    rbp
0x180013e57  push    rdi
0x180013e58  push    r14
0x180013e5a  lea     rbp, [rsp-760h]
0x180013e62  sub     rsp, 860h
0x180013e69  mov     rax, cs:__security_cookie
0x180013e70  xor     rax, rsp
0x180013e73  mov     [rbp+770h+var_20], rax
0x180013e7a  xor     r14d, r14d
0x180013e7d  mov     rsi, rcx
0x180013e80  mov     [rsp+870h+var_840], r14d
0x180013e85  mov     edi, r14d
0x180013e88  mov     [rsp+870h+Properties], r14
0x180013e8d  test    rcx, rcx
0x180013e90  jnz     short loc_180013E9C
0x180013e92  mov     ebx, 80070057h
0x180013e97  jmp     loc_180013F65
0x180013e9c  lea     rdx, [rsp+870h+var_840]; int *
0x180013ea1  call    ?GetTraceSessionStatus@CEtwLogHelper@@SAJPEBGAEAJ@Z; CEtwLogHelper::GetTraceSessionStatus(ushort const *,long &)
0x180013ea6  mov     ebx, eax
0x180013ea8  test    eax, eax
0x180013eaa  js      loc_180013F65
0x180013eb0  cmp     [rsp+870h+var_840], r14d
0x180013eb5  jnz     short loc_180013EBF
0x180013eb7  mov     ebx, r14d
0x180013eba  jmp     loc_180013F65
0x180013ebf  lea     rcx, [rsp+870h+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x180013ec4  call    ?CreateSessionProperty@CEtwLogHelper@@SAJAEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; CEtwLogHelper::CreateSessionProperty(_EVENT_TRACE_PROPERTIES * &)
0x180013ec9  mov     rdi, [rsp+870h+Properties]
0x180013ece  mov     ebx, eax
0x180013ed0  test    eax, eax
0x180013ed2  js      loc_180013F65
0x180013ed8  mov     r9d, 1; ControlCode
0x180013ede  mov     r8, rdi; Properties
0x180013ee1  mov     rdx, rsi; InstanceName
0x180013ee4  xor     ecx, ecx; TraceHandle
0x180013ee6  call    cs:__imp_ControlTraceW
0x180013eec  mov     ebx, eax
0x180013eee  test    eax, eax
0x180013ef0  jz      short loc_180013EFF
0x180013ef2  jle     short loc_180013F65
0x180013ef4  movzx   ebx, ax
0x180013ef7  or      ebx, 80070000h
0x180013efd  jmp     short loc_180013F65
0x180013eff  mov     eax, [rdi+70h]
0x180013f02  lea     r8, [rsp+870h+var_830]
0x180013f07  add     rax, rdi
0x180013f0a  mov     ecx, 7FFFFFFEh
0x180013f0f  mov     edx, 401h
0x180013f14  test    rcx, rcx
0x180013f17  jz      short loc_180013F38
0x180013f19  movzx   r9d, word ptr [rax]
0x180013f1d  test    r9w, r9w
0x180013f21  jz      short loc_180013F38
0x180013f23  mov     [r8], r9w
0x180013f27  add     rax, 2
0x180013f2b  add     r8, 2
0x180013f2f  dec     rcx
0x180013f32  sub     rdx, 1
0x180013f36  jnz     short loc_180013F14
0x180013f38  mov     rax, rdx
0x180013f3b  lea     rcx, [r8-2]
0x180013f3f  neg     rax
0x180013f42  sbb     ebx, ebx
0x180013f44  not     ebx
0x180013f46  and     ebx, 8007007Ah
0x180013f4c  test    rdx, rdx
0x180013f4f  cmovnz  rcx, r8
0x180013f53  mov     [rcx], r14w
0x180013f57  jz      short loc_180013F65
0x180013f59  lea     rcx, [rsp+870h+var_830]; unsigned __int16 *
0x180013f5e  call    ?CreateDecodedEtlFile@CEtwLogHelper@@SAJPEBG@Z; CEtwLogHelper::CreateDecodedEtlFile(ushort const *)
0x180013f63  mov     ebx, eax
0x180013f65  mov     eax, cs:dword_180048E90
0x180013f6b  cmp     eax, 5
0x180013f6e  jbe     short loc_180013FA7
0x180013f70  test    rsi, rsi
0x180013f73  mov     [rsp+870h+var_840], ebx
0x180013f77  lea     rax, String2
0x180013f7e  cmovz   rsi, rax
0x180013f82  lea     rdx, word_18004015A
0x180013f89  lea     rax, [rsp+870h+var_840]
0x180013f8e  mov     [rsp+870h+Properties], rsi
0x180013f93  mov     [rsp+870h+var_848], rax
0x180013f98  lea     rax, [rsp+870h+Properties]
0x180013f9d  mov     [rsp+870h+var_850], rax
0x180013fa2  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180013fa7  test    rdi, rdi
0x180013faa  jz      short loc_180013FB5
0x180013fac  mov     rcx, rdi; pv
0x180013faf  call    cs:__imp_CoTaskMemFree
0x180013fb5  mov     eax, ebx
0x180013fb7  mov     rcx, [rbp+770h+var_20]
0x180013fbe  xor     rcx, rsp; StackCookie
0x180013fc1  call    __security_check_cookie
0x180013fc6  lea     r11, [rsp+870h+var_10]
0x180013fce  mov     rbx, [r11+28h]
0x180013fd2  mov     rsi, [r11+30h]
0x180013fd6  mov     rsp, r11
0x180013fd9  pop     r14
0x180013fdb  pop     rdi
0x180013fdc  pop     rbp
0x180013fdd  retn
```
