# CEtwLogHelper::StopTraceSession(ushort const *)

- ea: `0x1800148f0`
- end: `0x180014a8f`
- name: `?StopTraceSession@CEtwLogHelper@@SAJPEBG@Z`
- size: `415`
- prototype: `__int64 __fastcall(LPCWSTR InstanceName)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f170`

## callees

- `0x1800011ac`
- `0x180001b90`
- `0x180014270`
- `0x1800143b8`
- `0x1800144bc`
- `0x1800148f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a59`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18001498a`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18001498a`

## pseudocode

```c
__int64 __fastcall CEtwLogHelper::StopTraceSession(
        unsigned __int16 *InstanceName,
        __int64 a2,
        unsigned __int16 *a3,
        int a4)
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
              TraceSessionStatus = CEtwLogHelper::CreateDecodedEtlFile(v15, v11, (int)a3, a4);
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
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v13 = TraceSessionStatus;
    if ( !v4 )
      v4 = (WCHAR *)&String2;
    Properties = (PEVENT_TRACE_PROPERTIES)v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (_DWORD)InstanceName,
      (unsigned int)word_18004215A,
      (_DWORD)a3,
      a4,
      (__int64)&Properties,
      (__int64)&v13);
  }
  if ( v5 )
    CoTaskMemFree(v5);
  return (unsigned int)TraceSessionStatus;
}

```

## disassembly

```asm
0x1800148f0  mov     [rsp-8+arg_8], rbx
0x1800148f5  mov     [rsp-8+arg_10], rsi
0x1800148fa  push    rbp
0x1800148fb  push    rdi
0x1800148fc  push    r14
0x1800148fe  lea     rbp, [rsp-760h]
0x180014906  sub     rsp, 860h
0x18001490d  mov     rax, cs:__security_cookie
0x180014914  xor     rax, rsp
0x180014917  mov     [rbp+770h+var_20], rax
0x18001491e  xor     r14d, r14d
0x180014921  mov     rsi, rcx
0x180014924  mov     [rsp+870h+var_840], r14d
0x180014929  mov     edi, r14d
0x18001492c  mov     [rsp+870h+Properties], r14
0x180014931  test    rcx, rcx
0x180014934  jnz     short loc_180014940
0x180014936  mov     ebx, 80070057h
0x18001493b  jmp     loc_180014A0F
0x180014940  lea     rdx, [rsp+870h+var_840]; int *
0x180014945  call    ?GetTraceSessionStatus@CEtwLogHelper@@SAJPEBGAEAJ@Z; CEtwLogHelper::GetTraceSessionStatus(ushort const *,long &)
0x18001494a  mov     ebx, eax
0x18001494c  test    eax, eax
0x18001494e  js      loc_180014A0F
0x180014954  cmp     [rsp+870h+var_840], r14d
0x180014959  jnz     short loc_180014963
0x18001495b  mov     ebx, r14d
0x18001495e  jmp     loc_180014A0F
0x180014963  lea     rcx, [rsp+870h+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x180014968  call    ?CreateSessionProperty@CEtwLogHelper@@SAJAEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; CEtwLogHelper::CreateSessionProperty(_EVENT_TRACE_PROPERTIES * &)
0x18001496d  mov     rdi, [rsp+870h+Properties]
0x180014972  mov     ebx, eax
0x180014974  test    eax, eax
0x180014976  js      loc_180014A0F
0x18001497c  mov     r9d, 1; ControlCode
0x180014982  mov     r8, rdi; Properties
0x180014985  mov     rdx, rsi; InstanceName
0x180014988  xor     ecx, ecx; TraceHandle
0x18001498a  call    cs:__imp_ControlTraceW
0x180014991  nop     dword ptr [rax+rax+00h]
0x180014996  mov     ebx, eax
0x180014998  test    eax, eax
0x18001499a  jz      short loc_1800149A9
0x18001499c  jle     short loc_180014A0F
0x18001499e  movzx   ebx, ax
0x1800149a1  or      ebx, 80070000h
0x1800149a7  jmp     short loc_180014A0F
0x1800149a9  mov     eax, [rdi+70h]
0x1800149ac  lea     r8, [rsp+870h+var_830]
0x1800149b1  add     rax, rdi
0x1800149b4  mov     ecx, 7FFFFFFEh
0x1800149b9  mov     edx, 401h
0x1800149be  test    rcx, rcx
0x1800149c1  jz      short loc_1800149E2
0x1800149c3  movzx   r9d, word ptr [rax]
0x1800149c7  test    r9w, r9w
0x1800149cb  jz      short loc_1800149E2
0x1800149cd  mov     [r8], r9w
0x1800149d1  add     rax, 2
0x1800149d5  add     r8, 2
0x1800149d9  dec     rcx
0x1800149dc  sub     rdx, 1
0x1800149e0  jnz     short loc_1800149BE
0x1800149e2  mov     rax, rdx
0x1800149e5  lea     rcx, [r8-2]
0x1800149e9  neg     rax
0x1800149ec  sbb     ebx, ebx
0x1800149ee  not     ebx
0x1800149f0  and     ebx, 8007007Ah
0x1800149f6  test    rdx, rdx
0x1800149f9  cmovnz  rcx, r8
0x1800149fd  mov     [rcx], r14w
0x180014a01  jz      short loc_180014A0F
0x180014a03  lea     rcx, [rsp+870h+var_830]; unsigned __int16 *
0x180014a08  call    ?CreateDecodedEtlFile@CEtwLogHelper@@SAJPEBG@Z; CEtwLogHelper::CreateDecodedEtlFile(ushort const *)
0x180014a0d  mov     ebx, eax
0x180014a0f  mov     eax, cs:dword_18004AE90
0x180014a15  cmp     eax, 5
0x180014a18  jbe     short loc_180014A51
0x180014a1a  test    rsi, rsi
0x180014a1d  mov     [rsp+870h+var_840], ebx
0x180014a21  lea     rax, String2
0x180014a28  cmovz   rsi, rax
0x180014a2c  lea     rdx, word_18004215A
0x180014a33  lea     rax, [rsp+870h+var_840]
0x180014a38  mov     [rsp+870h+Properties], rsi
0x180014a3d  mov     [rsp+870h+var_848], rax
0x180014a42  lea     rax, [rsp+870h+Properties]
0x180014a47  mov     [rsp+870h+var_850], rax
0x180014a4c  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180014a51  test    rdi, rdi
0x180014a54  jz      short loc_180014A65
0x180014a56  mov     rcx, rdi; pv
0x180014a59  call    cs:__imp_CoTaskMemFree
0x180014a60  nop     dword ptr [rax+rax+00h]
0x180014a65  mov     eax, ebx
0x180014a67  mov     rcx, [rbp+770h+var_20]
0x180014a6e  xor     rcx, rsp; StackCookie
0x180014a71  call    __security_check_cookie
0x180014a76  lea     r11, [rsp+870h+var_10]
0x180014a7e  mov     rbx, [r11+28h]
0x180014a82  mov     rsi, [r11+30h]
0x180014a86  mov     rsp, r11
0x180014a89  pop     r14
0x180014a8b  pop     rdi
0x180014a8c  pop     rbp
0x180014a8d  retn
```
