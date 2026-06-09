# NetSetupSvcWnf::Stop(void)

- ea: `0x180010608`
- end: `0x1800106bb`
- name: `?Stop@NetSetupSvcWnf@@QEAAXXZ`
- size: `179`
- prototype: `void __fastcall(NetSetupSvcWnf *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d04c`

## callees

- `0x180010608`
- `0x1800106c4`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180010625`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001066f`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180010625`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001066f`

## pseudocode

```c
void __fastcall NetSetupSvcWnf::Stop(NetSetupSvcWnf *this)
{
  int v2; // eax
  __int64 v3; // r8
  int v4; // eax
  __int64 v5; // r8

  if ( *((_QWORD *)this + 1) )
  {
    v2 = RtlUnsubscribeWnfNotificationWaitForCompletion();
    if ( v2 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v3 = (unsigned int)v2;
      LODWORD(v3) = v2 | 0x10000000;
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v3, (unsigned int)v2, v2 | 0x10000000);
    }
    *((_QWORD *)this + 1) = 0;
  }
  if ( *(_QWORD *)this )
  {
    v4 = RtlUnsubscribeWnfNotificationWaitForCompletion();
    if ( v4 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v5 = (unsigned int)v4;
      LODWORD(v5) = v4 | 0x10000000;
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v5, (unsigned int)v4, v4 | 0x10000000);
    }
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180010608  mov     [rsp+arg_0], rbx
0x18001060d  push    rdi
0x18001060e  sub     rsp, 30h
0x180010612  mov     rbx, rcx
0x180010615  lea     rdi, WPP_GLOBAL_Control
0x18001061c  mov     rcx, [rcx+8]
0x180010620  test    rcx, rcx
0x180010623  jz      short loc_180010667
0x180010625  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18001062b  test    eax, eax
0x18001062d  jns     short loc_18001065F
0x18001062f  mov     rcx, cs:WPP_GLOBAL_Control
0x180010636  cmp     rcx, rdi
0x180010639  jz      short loc_18001065F
0x18001063b  cmp     byte ptr [rcx+19h], 3
0x18001063f  jb      short loc_18001065F
0x180010641  mov     rcx, [rcx+10h]
0x180010645  mov     r8d, eax
0x180010648  bts     r8d, 1Ch
0x18001064d  mov     edx, 0Eh
0x180010652  mov     r9d, eax
0x180010655  mov     [rsp+38h+var_18], r8d
0x18001065a  call    WPP_SF_dd
0x18001065f  mov     qword ptr [rbx+8], 0
0x180010667  mov     rcx, [rbx]
0x18001066a  test    rcx, rcx
0x18001066d  jz      short loc_1800106B0
0x18001066f  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180010675  test    eax, eax
0x180010677  jns     short loc_1800106A9
0x180010679  mov     rcx, cs:WPP_GLOBAL_Control
0x180010680  cmp     rcx, rdi
0x180010683  jz      short loc_1800106A9
0x180010685  cmp     byte ptr [rcx+19h], 3
0x180010689  jb      short loc_1800106A9
0x18001068b  mov     rcx, [rcx+10h]
0x18001068f  mov     r8d, eax
0x180010692  bts     r8d, 1Ch
0x180010697  mov     edx, 0Fh
0x18001069c  mov     r9d, eax
0x18001069f  mov     [rsp+38h+var_18], r8d
0x1800106a4  call    WPP_SF_dd
0x1800106a9  mov     qword ptr [rbx], 0
0x1800106b0  mov     rbx, [rsp+38h+arg_0]
0x1800106b5  add     rsp, 30h
0x1800106b9  pop     rdi
0x1800106ba  retn
```
