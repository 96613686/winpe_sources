# BthEnumGenerateRfcommAepServiceId

- ea: `0x140018d54`
- end: `0x14001904f`
- name: `BthEnumGenerateRfcommAepServiceId`
- size: `763`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140019058`

## callees

- `0x140001294`
- `0x140001328`
- `0x1400013e8`
- `0x140018d54`

## import_xrefs

- `ntoskrnl!ExFreePool` at `0x14001901f`
- `ntoskrnl!ExFreePool` at `0x14001901f`
- `ntoskrnl!ExAllocatePool2` at `0x140018d91`
- `ntoskrnl!ExAllocatePool2` at `0x140018d91`

## string_xrefs

- `0x140018fc7`: `Bluetooth#Bluetooth%02.2x:%02.2x:%02.2x:%02.2x:%02.2x:%02.2x-%02.2x:%02.2x:%02.2x:%02.2x:%02.2x:%02.2x#RFCOMM:%08.8lx:{%08.8lx-%04.4hx-%04.4hx-%02.2hhx%02.2hhx-%02.2hhx%02.2hhx%02.2hhx%02.2hhx%02.2hhx%02.2hhx}`

## pseudocode

```c
__int64 __fastcall BthEnumGenerateRfcommAepServiceId(__int64 a1, wchar_t **a2)
{
  __int64 v2; // rax
  __int64 v4; // rdi
  int v5; // edx
  NTSTATUS v6; // edi
  __int64 v7; // rax
  __int64 v8; // rcx
  int v9; // edx
  __int64 v11; // [rsp+28h] [rbp-130h]
  wchar_t *pszDest; // [rsp+100h] [rbp-58h]

  v2 = *(_QWORD *)(a1 + 8);
  *a2 = 0;
  v4 = *(_QWORD *)(v2 + 64);
  pszDest = (wchar_t *)ExAllocatePool2(256, 220, 1330467906);
  if ( pszDest )
  {
    v7 = *(_QWORD *)(a1 + 192);
    v8 = *(_QWORD *)(v4 + 320);
    v6 = RtlStringCchPrintfW(
           pszDest,
           0x6Eu,
           L"Bluetooth#Bluetooth%02.2x:%02.2x:%02.2x:%02.2x:%02.2x:%02.2x-%02.2x:%02.2x:%02.2x:%02.2x:%02.2x:%02.2x#RFCOMM"
            ":%08.8lx:{%08.8lx-%04.4hx-%04.4hx-%02.2hhx%02.2hhx-%02.2hhx%02.2hhx%02.2hhx%02.2hhx%02.2hhx%02.2hhx}",
           BYTE5(v8),
           BYTE4(v8),
           BYTE3(v8),
           BYTE2(v8),
           BYTE1(v8),
           (unsigned __int8)v8,
           BYTE5(v7),
           BYTE4(v7),
           BYTE3(v7),
           BYTE2(v7),
           BYTE1(v7),
           (unsigned __int8)v7,
           *(_DWORD *)(a1 + 1072),
           *(_DWORD *)(a1 + 1056),
           *(unsigned __int16 *)(a1 + 1060),
           *(unsigned __int16 *)(a1 + 1062),
           *(unsigned __int8 *)(a1 + 1064),
           *(unsigned __int8 *)(a1 + 1065),
           *(unsigned __int8 *)(a1 + 1066),
           *(unsigned __int8 *)(a1 + 1067),
           *(unsigned __int8 *)(a1 + 1068),
           *(unsigned __int8 *)(a1 + 1069),
           *(unsigned __int8 *)(a1 + 1070),
           *(unsigned __int8 *)(a1 + 1071));
    if ( v6 >= 0 )
    {
      *a2 = pszDest;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v11) = v6;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          3,
          27,
          (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
          v11);
      }
      ExFreePool(pszDest);
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        3,
        26,
        (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids);
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140018d54  mov     [rsp+arg_8], rdx
0x140018d59  mov     [rsp+arg_0], rcx
0x140018d5e  push    rbx
0x140018d5f  push    rbp
0x140018d60  push    rsi
0x140018d61  push    rdi
0x140018d62  push    r12
0x140018d64  push    r13
0x140018d66  push    r14
0x140018d68  push    r15
0x140018d6a  sub     rsp, 118h
0x140018d71  mov     rax, [rcx+8]
0x140018d75  mov     rbx, rcx
0x140018d78  mov     qword ptr [rdx], 0
0x140018d7f  mov     r8d, 4F4D5442h
0x140018d85  mov     edx, 0DCh
0x140018d8a  mov     rdi, [rax+40h]
0x140018d8e  lea     ecx, [rdx+24h]
0x140018d91  call    cs:__imp_ExAllocatePool2
0x140018d98  nop     dword ptr [rax+rax+00h]
0x140018d9d  mov     [rsp+158h+pszDest], rax
0x140018da5  test    rax, rax
0x140018da8  jnz     short loc_140018DEA
0x140018daa  lea     rax, WPP_RECORDER_INITIALIZED
0x140018db1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018db8  jz      short loc_140018DE0
0x140018dba  mov     rcx, cs:WPP_GLOBAL_Control
0x140018dc1  lea     rax, WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids
0x140018dc8  mov     r9d, 1Ah
0x140018dce  mov     [rsp+158h+var_138], rax
0x140018dd3  mov     rcx, [rcx+40h]
0x140018dd7  lea     r8d, [r9-17h]
0x140018ddb  call    WPP_RECORDER_SF_
0x140018de0  mov     edi, 0C000009Ah
0x140018de5  jmp     loc_140019038
0x140018dea  mov     rax, [rbx+0C0h]
0x140018df1  mov     rcx, [rdi+140h]
0x140018df8  movzx   edx, byte ptr [rbx+42Bh]
0x140018dff  movzx   r14d, byte ptr [rbx+42Fh]
0x140018e07  movzx   r15d, byte ptr [rbx+42Eh]
0x140018e0f  movzx   r12d, byte ptr [rbx+42Dh]
0x140018e17  movzx   r13d, byte ptr [rbx+42Ch]
0x140018e1f  mov     [rsp+158h+arg_10], edx
0x140018e26  movzx   edx, byte ptr [rbx+42Ah]
0x140018e2d  mov     [rsp+158h+arg_18], edx
0x140018e34  movzx   edx, byte ptr [rbx+429h]
0x140018e3b  mov     [rsp+158h+var_78], edx
0x140018e42  movzx   edx, byte ptr [rbx+428h]
0x140018e49  mov     [rsp+158h+var_88], r14d
0x140018e51  mov     [rsp+158h+var_74], edx
0x140018e58  movzx   edx, word ptr [rbx+426h]
0x140018e5f  mov     [rsp+158h+var_90], r15d
0x140018e67  mov     [rsp+158h+var_70], edx
0x140018e6e  movzx   edx, word ptr [rbx+424h]
0x140018e75  mov     [rsp+158h+var_98], r12d
0x140018e7d  mov     [rsp+158h+var_6C], edx
0x140018e84  movzx   edx, al
0x140018e87  mov     [rsp+158h+var_A0], r13d
0x140018e8f  mov     [rsp+158h+var_68], edx
0x140018e96  mov     rdx, rax
0x140018e99  shr     rdx, 8
0x140018e9d  movzx   edx, dl
0x140018ea0  mov     [rsp+158h+var_64], edx
0x140018ea7  mov     rdx, rax
0x140018eaa  shr     rdx, 10h
0x140018eae  movzx   edx, dl
0x140018eb1  mov     [rsp+158h+var_60], edx
0x140018eb8  mov     rdx, rax
0x140018ebb  shr     rdx, 18h
0x140018ebf  movzx   ebp, dl
0x140018ec2  mov     rdx, rax
0x140018ec5  shr     rax, 28h
0x140018ec9  movzx   ebx, al
0x140018ecc  mov     rax, rcx
0x140018ecf  shr     rax, 8
0x140018ed3  movzx   r11d, al
0x140018ed7  mov     rax, rcx
0x140018eda  shr     rax, 10h
0x140018ede  movzx   r10d, al
0x140018ee2  mov     rax, rcx
0x140018ee5  shr     rax, 18h
0x140018ee9  movzx   r8d, al
0x140018eed  mov     rax, rcx
0x140018ef0  shr     rax, 20h
0x140018ef4  shr     rdx, 20h
0x140018ef8  movzx   esi, dl
0x140018efb  movzx   edx, al
0x140018efe  mov     eax, [rsp+158h+arg_10]
0x140018f05  mov     [rsp+158h+var_A8], eax
0x140018f0c  mov     eax, [rsp+158h+arg_18]
0x140018f13  mov     [rsp+158h+var_B0], eax
0x140018f1a  mov     eax, [rsp+158h+var_78]
0x140018f21  mov     [rsp+158h+var_B8], eax
0x140018f28  mov     eax, [rsp+158h+var_74]
0x140018f2f  mov     [rsp+158h+var_C0], eax
0x140018f36  mov     eax, [rsp+158h+var_70]
0x140018f3d  mov     [rsp+158h+var_C8], eax
0x140018f44  mov     eax, [rsp+158h+var_6C]
0x140018f4b  mov     [rsp+158h+var_D0], eax
0x140018f52  movzx   edi, cl
0x140018f55  shr     rcx, 28h
0x140018f59  movzx   r9d, cl
0x140018f5d  mov     rcx, [rsp+158h+arg_0]
0x140018f65  mov     eax, [rcx+420h]
0x140018f6b  mov     [rsp+158h+var_D8], eax
0x140018f72  mov     eax, [rcx+430h]
0x140018f78  mov     [rsp+158h+var_E0], eax
0x140018f7c  mov     eax, [rsp+158h+var_68]
0x140018f83  mov     [rsp+158h+var_E8], eax
0x140018f87  mov     eax, [rsp+158h+var_64]
0x140018f8e  mov     [rsp+158h+var_F0], eax
0x140018f92  mov     eax, [rsp+158h+var_60]
0x140018f99  mov     [rsp+158h+var_F8], eax
0x140018f9d  mov     [rsp+158h+var_100], ebp
0x140018fa1  mov     [rsp+158h+var_108], esi
0x140018fa5  mov     [rsp+158h+var_110], ebx
0x140018fa9  mov     rbx, [rsp+158h+pszDest]
0x140018fb1  mov     [rsp+158h+var_118], edi
0x140018fb5  mov     rcx, rbx; pszDest
0x140018fb8  mov     [rsp+158h+var_120], r11d
0x140018fbd  mov     [rsp+158h+var_128], r10d
0x140018fc2  mov     dword ptr [rsp+158h+var_130], r8d
0x140018fc7  lea     r8, aBluetoothBluet_0; "Bluetooth#Bluetooth%02.2x:%02.2x:%02.2x"...
0x140018fce  mov     dword ptr [rsp+158h+var_138], edx
0x140018fd2  mov     edx, 6Eh ; 'n'; cchDest
0x140018fd7  call    RtlStringCchPrintfW
0x140018fdc  mov     edi, eax
0x140018fde  test    eax, eax
0x140018fe0  jns     short loc_14001902D
0x140018fe2  lea     rax, WPP_RECORDER_INITIALIZED
0x140018fe9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018ff0  jz      short loc_14001901C
0x140018ff2  mov     rcx, cs:WPP_GLOBAL_Control
0x140018ff9  lea     rax, WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids
0x140019000  mov     r9d, 1Bh
0x140019006  mov     dword ptr [rsp+158h+var_130], edi
0x14001900a  mov     [rsp+158h+var_138], rax
0x14001900f  mov     rcx, [rcx+40h]
0x140019013  lea     r8d, [r9-18h]
0x140019017  call    WPP_RECORDER_SF_d
0x14001901c  mov     rcx, rbx; P
0x14001901f  call    cs:__imp_ExFreePool
0x140019026  nop     dword ptr [rax+rax+00h]
0x14001902b  jmp     short loc_140019038
0x14001902d  mov     rax, [rsp+158h+arg_8]
0x140019035  mov     [rax], rbx
0x140019038  mov     eax, edi
0x14001903a  add     rsp, 118h
0x140019041  pop     r15
0x140019043  pop     r14
0x140019045  pop     r13
0x140019047  pop     r12
0x140019049  pop     rdi
0x14001904a  pop     rsi
0x14001904b  pop     rbp
0x14001904c  pop     rbx
0x14001904d  retn
```
