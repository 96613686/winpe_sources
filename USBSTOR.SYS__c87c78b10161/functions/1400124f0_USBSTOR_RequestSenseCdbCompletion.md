# USBSTOR_RequestSenseCdbCompletion

- ea: `0x1400124f0`
- end: `0x140012722`
- name: `USBSTOR_RequestSenseCdbCompletion`
- size: `562`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140001008`
- `0x140003630`
- `0x140004910`
- `0x140009f90`
- `0x1400105e8`
- `0x140010664`
- `0x140010c60`
- `0x140011e3c`
- `0x1400124f0`

## pseudocode

```c
__int64 __fastcall USBSTOR_RequestSenseCdbCompletion(_QWORD *a1, __int64 a2, __int64 a3)
{
  _DWORD *v6; // rsi
  void *v7; // rbp
  __int64 v8; // r14
  __int64 v10; // r8
  __int64 v11; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 117, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  USBSTOR_LogEntry(1128485714, a1, a2, *(int *)(a2 + 48));
  v6 = (_DWORD *)a1[8];
  if ( *v6 == 558842960 )
  {
    a1 = (_QWORD *)*((_QWORD *)v6 + 2);
    v7 = v6;
    v6 = (_DWORD *)a1[8];
  }
  else
  {
    v7 = 0;
    if ( *v6 != 558842950 )
    {
      v6 = 0;
      a1 = 0;
    }
  }
  v8 = *(_QWORD *)(*(_QWORD *)(a2 + 184) + 8LL);
  if ( (unsigned __int8)USBSTOR_CheckRequestTimeOut(a1) )
  {
    USBSTOR_LogEntry(828601202, a1, a2, v8);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 118, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    return 0;
  }
  else
  {
    v10 = (int)v6[99];
    v11 = *(int *)(a2 + 48);
    if ( (int)v11 >= 0 )
    {
      USBSTOR_LogEntry(862155634, v11, v10, 0);
      USBSTOR_IssueRequestSenseBulkRequest(a1, a2, a3);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 121, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
      }
      return 3221225494LL;
    }
    else
    {
      USBSTOR_LogEntry(845378418, v11, v10, 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_DD(
          WPP_GLOBAL_Control->AttachedDevice,
          119,
          WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids,
          *(unsigned int *)(a2 + 48),
          v6[99]);
      }
      *(_QWORD *)(a2 + 56) = 0;
      *(_DWORD *)(a2 + 48) = -1073741435;
      *(_BYTE *)(v8 + 3) = 14;
      USBSTOR_TranslateCDBComplete(a1, a2, v8);
      USBSTOR_QueueResetDevice(a1, v7);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 120, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
      }
      return 3221225861LL;
    }
  }
}

```

## disassembly

```asm
0x1400124f0  mov     [rsp+arg_8], rbx
0x1400124f5  mov     [rsp+arg_10], rbp
0x1400124fa  push    rsi
0x1400124fb  push    rdi
0x1400124fc  push    r13
0x1400124fe  push    r14
0x140012500  push    r15
0x140012502  sub     rsp, 30h
0x140012506  mov     r15, r8
0x140012509  mov     [rsp+58h+arg_0], 0
0x140012511  mov     rdi, rdx
0x140012514  mov     rbx, rcx
0x140012517  mov     rcx, cs:WPP_GLOBAL_Control
0x14001251e  lea     rax, WPP_GLOBAL_Control
0x140012525  lea     r13, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14001252c  cmp     rcx, rax
0x14001252f  jz      short loc_14001254F
0x140012531  mov     eax, [rcx+2Ch]
0x140012534  test    al, 1
0x140012536  jz      short loc_14001254F
0x140012538  cmp     byte ptr [rcx+29h], 5
0x14001253c  jb      short loc_14001254F
0x14001253e  mov     rcx, [rcx+18h]
0x140012542  mov     edx, 75h ; 'u'
0x140012547  mov     r8, r13
0x14001254a  call    WPP_SF_
0x14001254f  movsxd  r9, dword ptr [rdi+30h]
0x140012553  mov     r8, rdi
0x140012556  mov     rdx, rbx
0x140012559  mov     ecx, 43435352h
0x14001255e  call    USBSTOR_LogEntry
0x140012563  mov     rsi, [rbx+40h]
0x140012567  mov     eax, [rsi]
0x140012569  cmp     eax, 214F4450h
0x14001256e  jnz     short loc_14001257D
0x140012570  mov     rbx, [rsi+10h]
0x140012574  mov     rbp, rsi
0x140012577  mov     rsi, [rbx+40h]
0x14001257b  jmp     short loc_14001258A
0x14001257d  xor     ebp, ebp
0x14001257f  cmp     eax, 214F4446h
0x140012584  jz      short loc_14001258A
0x140012586  xor     esi, esi
0x140012588  xor     ebx, ebx
0x14001258a  mov     rax, [rdi+0B8h]
0x140012591  lea     r9, [rsp+58h+arg_0]
0x140012596  mov     rdx, rdi
0x140012599  mov     rcx, rbx; Object
0x14001259c  mov     r14, [rax+8]
0x1400125a0  mov     r8, r14
0x1400125a3  call    USBSTOR_CheckRequestTimeOut
0x1400125a8  test    al, al
0x1400125aa  jz      short loc_1400125F9
0x1400125ac  mov     r9, r14
0x1400125af  mov     r8, rdi
0x1400125b2  mov     rdx, rbx
0x1400125b5  mov     ecx, 31637372h
0x1400125ba  call    USBSTOR_LogEntry
0x1400125bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400125c6  lea     r15, WPP_GLOBAL_Control
0x1400125cd  cmp     rcx, r15
0x1400125d0  jz      short loc_1400125F0
0x1400125d2  mov     eax, [rcx+2Ch]
0x1400125d5  test    al, 1
0x1400125d7  jz      short loc_1400125F0
0x1400125d9  cmp     byte ptr [rcx+29h], 2
0x1400125dd  jb      short loc_1400125F0
0x1400125df  mov     rcx, [rcx+18h]
0x1400125e3  mov     edx, 76h ; 'v'
0x1400125e8  mov     r8, r13
0x1400125eb  call    WPP_SF_
0x1400125f0  mov     eax, [rsp+58h+arg_0]
0x1400125f4  jmp     loc_14001270A
0x1400125f9  movsxd  rax, dword ptr [rdi+30h]
0x1400125fd  xor     r9d, r9d
0x140012600  movsxd  r8, dword ptr [rsi+18Ch]
0x140012607  mov     rdx, rax
0x14001260a  test    eax, eax
0x14001260c  jns     loc_1400126B8
0x140012612  mov     ecx, 32637372h
0x140012617  call    USBSTOR_LogEntry
0x14001261c  mov     rcx, cs:WPP_GLOBAL_Control
0x140012623  lea     r15, WPP_GLOBAL_Control
0x14001262a  cmp     rcx, r15
0x14001262d  jz      short loc_14001265B
0x14001262f  mov     eax, [rcx+2Ch]
0x140012632  test    al, 1
0x140012634  jz      short loc_14001265B
0x140012636  cmp     byte ptr [rcx+29h], 2
0x14001263a  jb      short loc_14001265B
0x14001263c  mov     eax, [rsi+18Ch]
0x140012642  mov     edx, 77h ; 'w'
0x140012647  mov     r9d, [rdi+30h]
0x14001264b  mov     r8, r13
0x14001264e  mov     rcx, [rcx+18h]
0x140012652  mov     [rsp+58h+var_38], eax
0x140012656  call    WPP_SF_DD
0x14001265b  mov     qword ptr [rdi+38h], 0
0x140012663  mov     esi, 0C0000185h
0x140012668  mov     [rdi+30h], esi
0x14001266b  mov     r8, r14
0x14001266e  mov     rdx, rdi
0x140012671  mov     byte ptr [r14+3], 0Eh
0x140012676  mov     rcx, rbx; Object
0x140012679  call    USBSTOR_TranslateCDBComplete
0x14001267e  mov     rdx, rbp; Context
0x140012681  mov     rcx, rbx; Object
0x140012684  call    USBSTOR_QueueResetDevice
0x140012689  mov     rcx, cs:WPP_GLOBAL_Control
0x140012690  cmp     rcx, r15
0x140012693  jz      short loc_1400126B4
0x140012695  mov     edx, [rcx+2Ch]
0x140012698  test    dl, 1
0x14001269b  jz      short loc_1400126B4
0x14001269d  cmp     byte ptr [rcx+29h], 2
0x1400126a1  jb      short loc_1400126B4
0x1400126a3  mov     rcx, [rcx+18h]
0x1400126a7  mov     edx, 78h ; 'x'
0x1400126ac  mov     r8, r13
0x1400126af  call    WPP_SF_
0x1400126b4  mov     eax, esi
0x1400126b6  jmp     short loc_14001270A
0x1400126b8  mov     ecx, 33637372h
0x1400126bd  call    USBSTOR_LogEntry
0x1400126c2  mov     r8, r15
0x1400126c5  mov     rdx, rdi
0x1400126c8  mov     rcx, rbx
0x1400126cb  call    USBSTOR_IssueRequestSenseBulkRequest
0x1400126d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400126d7  lea     r15, WPP_GLOBAL_Control
0x1400126de  cmp     rcx, r15
0x1400126e1  jz      short loc_140012705
0x1400126e3  mov     edx, [rcx+2Ch]
0x1400126e6  test    dl, 1
0x1400126e9  jz      short loc_140012705
0x1400126eb  cmp     byte ptr [rcx+29h], 5
0x1400126ef  jb      short loc_140012705
0x1400126f1  mov     rcx, [rcx+18h]
0x1400126f5  mov     edx, 79h ; 'y'
0x1400126fa  mov     r9d, eax
0x1400126fd  mov     r8, r13
0x140012700  call    WPP_SF_d
0x140012705  mov     eax, 0C0000016h
0x14001270a  mov     rbx, [rsp+58h+arg_8]
0x14001270f  mov     rbp, [rsp+58h+arg_10]
0x140012714  add     rsp, 30h
0x140012718  pop     r15
0x14001271a  pop     r14
0x14001271c  pop     r13
0x14001271e  pop     rdi
0x14001271f  pop     rsi
0x140012720  retn
```
