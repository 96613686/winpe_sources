# DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::RemoveTargetDetermined<ushort (&)[40]>(ushort (&)[40])

- ea: `0x18000570c`
- end: `0x1800057e2`
- name: `??$RemoveTargetDetermined@AEAY0CI@G@RemoveDeviceActivity@DeviceCenterContextHandlersTelemetry@@QEAAXAEAY0CI@G@Z`
- size: `214`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180007a10`

## callees

- `0x1800018dc`
- `0x18000570c`
- `0x180009170`
- `0x18000c990`

## pseudocode

```c
int __fastcall DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::RemoveTargetDetermined<unsigned short (&)[40]>(
        __int64 a1,
        __int64 *a2)
{
  __int64 v4; // rax
  __int64 v5; // r10
  const GUID *v6; // r8
  __int64 v7; // rax
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-48h] BYREF
  __int64 *v11; // [rsp+50h] [rbp-28h]
  int v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+5Ch] [rbp-1Ch]

  v4 = (__int64)DeviceCenterContextHandlersLogging::Provider();
  v5 = v4;
  if ( *(_DWORD *)v4 > 5u )
  {
    v4 = *(_QWORD *)(v4 + 24);
    if ( (*(_QWORD *)(v5 + 16) & 0x200000000000LL) != 0 && (v4 & 0x200000000000LL) == v4 )
    {
      v6 = (const GUID *)(*(_QWORD *)(a1 + 272) + 8LL);
      if ( a2 )
      {
        v7 = -1;
        do
          ++v7;
        while ( *((_WORD *)a2 + v7) );
        v8 = 2 * v7 + 2;
      }
      else
      {
        a2 = &qword_180010930;
        v8 = 2;
      }
      v12 = v8;
      v13 = 0;
      v11 = a2;
      LODWORD(v4) = tlgWriteTransfer_EventWriteTransfer(v5, (unsigned __int8 *)byte_180010DFD, v6, 0, 3u, &v10);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000570c  mov     [rsp+arg_8], rbx
0x180005711  push    rdi
0x180005712  sub     rsp, 70h
0x180005716  mov     rax, cs:__security_cookie
0x18000571d  xor     rax, rsp
0x180005720  mov     [rsp+78h+var_18], rax
0x180005725  mov     rbx, rdx
0x180005728  mov     rdi, rcx
0x18000572b  call    ?Provider@DeviceCenterContextHandlersLogging@@SAPEBU_tlgProvider_t@@XZ; DeviceCenterContextHandlersLogging::Provider(void)
0x180005730  mov     r10, rax
0x180005733  mov     r8d, [rax]
0x180005736  cmp     r8d, 5
0x18000573a  jbe     loc_1800057C7
0x180005740  mov     rax, [rax+18h]
0x180005744  mov     rdx, 200000000000h
0x18000574e  mov     r8, [r10+10h]
0x180005752  test    rdx, r8
0x180005755  jz      short loc_1800057C7
0x180005757  mov     rcx, rax
0x18000575a  and     rcx, rdx
0x18000575d  cmp     rcx, rax
0x180005760  jnz     short loc_1800057C7
0x180005762  mov     r8, [rdi+110h]
0x180005769  xor     ecx, ecx
0x18000576b  add     r8, 8
0x18000576f  test    rbx, rbx
0x180005772  jz      short loc_18000578A
0x180005774  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005778  inc     rax
0x18000577b  cmp     [rbx+rax*2], cx
0x18000577f  jnz     short loc_180005778
0x180005781  lea     eax, ds:2[rax*2]
0x180005788  jmp     short loc_180005796
0x18000578a  lea     rbx, qword_180010930
0x180005791  mov     eax, 2
0x180005796  mov     [rsp+78h+var_20], eax
0x18000579a  lea     rdx, byte_180010DFD
0x1800057a1  lea     rax, [rsp+78h+var_48]
0x1800057a6  mov     [rsp+78h+var_1C], ecx
0x1800057aa  mov     [rsp+78h+var_50], rax
0x1800057af  xor     r9d, r9d
0x1800057b2  mov     rcx, r10
0x1800057b5  mov     [rsp+78h+var_58], 3
0x1800057bd  mov     [rsp+78h+var_28], rbx
0x1800057c2  call    _tlgWriteTransfer_EventWriteTransfer
0x1800057c7  mov     rcx, [rsp+78h+var_18]
0x1800057cc  xor     rcx, rsp; StackCookie
0x1800057cf  call    __security_check_cookie
0x1800057d4  mov     rbx, [rsp+78h+arg_8]
0x1800057dc  add     rsp, 70h
0x1800057e0  pop     rdi
0x1800057e1  retn
```
