# MbbIpBuildInterfaceRegistryPath(_GUID *,uchar,ulong *,ushort * *)

- ea: `0x14004253c`
- end: `0x140042830`
- name: `?MbbIpBuildInterfaceRegistryPath@@YAJPEAU_GUID@@EPEAKPEAPEAG@Z`
- size: `756`
- prototype: `__int64 __fastcall(GUID *Guid, char, unsigned int *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x140042838`
- `0x1400432ec`

## callees

- `0x140001cf8`
- `0x140001db8`
- `0x14004253c`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x140042810`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140042810`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14004256d`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14004256d`
- `ntoskrnl!RtlStringFromGUID` at `0x140042594`
- `ntoskrnl!RtlStringFromGUID` at `0x140042594`
- `ntoskrnl!ExAllocatePool2` at `0x14004264b`
- `ntoskrnl!ExAllocatePool2` at `0x14004264b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400427f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400427f8`

## string_xrefs

- `0x1400425f8`: `\Registry\Machine\System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces\`
- `0x1400425ff`: `\Registry\Machine\System\CurrentControlSet\Services\Tcpip6\Parameters\Interfaces\`
- `0x14004262b`: `\Registry\Machine\OSDATA\Networking\Dhcp\Client4\`
- `0x14004261a`: `\Registry\Machine\OSDATA\Networking\Dhcp\Client6\`

## pseudocode

```c
__int64 __fastcall MbbIpBuildInterfaceRegistryPath(GUID *Guid, char a2, unsigned int *a3, unsigned __int16 **a4)
{
  int v8; // edx
  unsigned int v9; // ebx
  const wchar_t *v10; // rsi
  unsigned int v11; // ebx
  unsigned int v12; // ebp
  unsigned __int16 *v13; // rdx
  unsigned __int16 *Pool2; // r14
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // rax
  unsigned __int16 *v17; // r8
  unsigned __int16 *v18; // rcx
  unsigned __int64 v19; // rcx
  unsigned __int16 *v20; // rax
  unsigned __int64 v21; // rax
  wchar_t *Buffer; // r8
  unsigned __int64 v23; // rcx
  unsigned __int64 i; // rdi
  unsigned __int16 *v25; // rcx
  int v26; // r9d
  struct _UNICODE_STRING GuidString; // [rsp+30h] [rbp-58h] BYREF

  GuidString = 0;
  if ( !dword_14005F500 )
  {
    dword_14005F4FC = (unsigned __int8)RtlIsStateSeparationEnabled();
    dword_14005F500 = 1;
  }
  v9 = RtlStringFromGUID(Guid, &GuidString);
  if ( v9 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        2,
        51,
        (__int64)WPP_f53708f2277a3aabca584f524242a299_Traceguids,
        v9);
    }
    goto LABEL_46;
  }
  if ( dword_14005F4FC )
  {
    v10 = L"\\Registry\\Machine\\OSDATA\\Networking\\Dhcp\\Client6\\";
    v11 = 100;
    if ( !a2 )
      v10 = L"\\Registry\\Machine\\OSDATA\\Networking\\Dhcp\\Client4\\";
  }
  else
  {
    v10 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Interfaces\\";
    if ( !a2 )
      v10 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces\\";
    v11 = a2 != 0 ? 164 : 162;
  }
  v12 = v11 + GuidString.Length;
  Pool2 = (unsigned __int16 *)ExAllocatePool2(256, v12 + 2, 1682129485);
  if ( Pool2 )
  {
    v15 = (unsigned __int64)(v12 + 2) >> 1;
    if ( v15 )
    {
      v13 = (unsigned __int16 *)((unsigned __int64)(v12 + 2) >> 1);
      v16 = (unsigned __int64)v11 >> 1;
      v17 = Pool2;
      do
      {
        if ( !v16 )
          break;
        if ( !*v10 )
          break;
        *v17++ = *v10++;
        --v16;
        v13 = (unsigned __int16 *)((char *)v13 - 1);
      }
      while ( v13 );
      v18 = v17 - 1;
      v9 = v13 == 0 ? 0x80000005 : 0;
      if ( v13 )
        v18 = v17;
      *v18 = 0;
      if ( v13 )
      {
        v19 = (unsigned __int64)(v12 + 2) >> 1;
        v20 = Pool2;
        do
        {
          if ( !*v20 )
            break;
          ++v20;
          --v19;
        }
        while ( v19 );
        v9 = v19 == 0 ? 0xC000000D : 0;
        if ( v19 )
          v21 = v15 - v19;
        else
          v21 = 0;
        if ( v19 )
        {
          v13 = &Pool2[v21];
          Buffer = GuidString.Buffer;
          v23 = (unsigned __int64)GuidString.Length >> 1;
          for ( i = v15 - v21; i; --i )
          {
            if ( !v23 )
              break;
            if ( !*Buffer )
              break;
            *v13++ = *Buffer++;
            --v23;
          }
          v25 = v13 - 1;
          if ( i )
            v25 = v13;
          v9 = i == 0 ? 0x80000005 : 0;
          *v25 = 0;
          if ( i )
          {
            *a4 = Pool2;
            *a3 = v12;
            goto LABEL_46;
          }
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_45;
        v26 = 54;
        goto LABEL_44;
      }
    }
    else
    {
      v9 = -1073741811;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_45:
      ExFreePoolWithTag(Pool2, 0);
      goto LABEL_46;
    }
    v26 = 53;
LABEL_44:
    LOBYTE(v13) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v13,
      2,
      v26,
      (__int64)WPP_f53708f2277a3aabca584f524242a299_Traceguids);
    goto LABEL_45;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v13) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v13,
      2,
      52,
      (__int64)WPP_f53708f2277a3aabca584f524242a299_Traceguids);
  }
  v9 = -1073741670;
LABEL_46:
  if ( GuidString.Buffer )
    RtlFreeUnicodeString(&GuidString);
  return v9;
}

```

## disassembly

```asm
0x14004253c  push    rbx
0x14004253e  push    rbp
0x14004253f  push    rsi
0x140042540  push    rdi
0x140042541  push    r12
0x140042543  push    r13
0x140042545  push    r14
0x140042547  push    r15
0x140042549  sub     rsp, 48h
0x14004254d  xor     r13d, r13d
0x140042550  xorps   xmm0, xmm0
0x140042553  cmp     cs:dword_14005F500, r13d
0x14004255a  mov     r15, r9
0x14004255d  mov     r12, r8
0x140042560  mov     dil, dl
0x140042563  mov     rbx, rcx
0x140042566  movups  xmmword ptr [rsp+88h+GuidString.Length], xmm0
0x14004256b  jnz     short loc_14004258C
0x14004256d  call    cs:__imp_RtlIsStateSeparationEnabled
0x140042574  nop     dword ptr [rax+rax+00h]
0x140042579  movzx   eax, al
0x14004257c  mov     cs:dword_14005F4FC, eax
0x140042582  mov     cs:dword_14005F500, 1
0x14004258c  lea     rdx, [rsp+88h+GuidString]; GuidString
0x140042591  mov     rcx, rbx; Guid
0x140042594  call    cs:__imp_RtlStringFromGUID
0x14004259b  nop     dword ptr [rax+rax+00h]
0x1400425a0  mov     ebx, eax
0x1400425a2  test    eax, eax
0x1400425a4  jz      short loc_1400425EC
0x1400425a6  lea     rax, WPP_RECORDER_INITIALIZED
0x1400425ad  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400425b4  jz      loc_140042804
0x1400425ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400425c1  lea     rax, WPP_f53708f2277a3aabca584f524242a299_Traceguids
0x1400425c8  mov     r9d, 33h ; '3'
0x1400425ce  mov     [rsp+88h+var_60], ebx
0x1400425d2  mov     [rsp+88h+var_68], rax
0x1400425d7  mov     rcx, [rcx+40h]
0x1400425db  lea     r8d, [r9-31h]
0x1400425df  mov     dl, r8b
0x1400425e2  call    WPP_RECORDER_SF_d
0x1400425e7  jmp     loc_140042804
0x1400425ec  cmp     cs:dword_14005F4FC, r13d
0x1400425f3  jnz     short loc_14004261A
0x1400425f5  test    dil, dil
0x1400425f8  lea     rax, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400425ff  lea     rsi, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x140042606  cmovz   rsi, rax
0x14004260a  neg     dil
0x14004260d  sbb     ebx, ebx
0x14004260f  and     ebx, 2
0x140042612  add     ebx, 0A2h
0x140042618  jmp     short loc_140042632
0x14004261a  lea     rsi, aRegistryMachin_0; "\\Registry\\Machine\\OSDATA\\Networking"...
0x140042621  mov     ebx, 64h ; 'd'
0x140042626  test    dil, dil
0x140042629  jnz     short loc_140042632
0x14004262b  lea     rsi, aRegistryMachin_1; "\\Registry\\Machine\\OSDATA\\Networking"...
0x140042632  movzx   ebp, [rsp+88h+GuidString.Length]
0x140042637  mov     r8d, 6443424Dh
0x14004263d  add     ebp, ebx
0x14004263f  mov     ecx, 100h
0x140042644  lea     eax, [rbp+2]
0x140042647  mov     edx, eax
0x140042649  mov     edi, eax
0x14004264b  call    cs:__imp_ExAllocatePool2
0x140042652  nop     dword ptr [rax+rax+00h]
0x140042657  mov     r14, rax
0x14004265a  test    rax, rax
0x14004265d  jnz     short loc_1400426A0
0x14004265f  lea     rax, WPP_RECORDER_INITIALIZED
0x140042666  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004266d  jz      short loc_140042696
0x14004266f  mov     rcx, cs:WPP_GLOBAL_Control
0x140042676  lea     r8d, [r14+2]
0x14004267a  lea     rax, WPP_f53708f2277a3aabca584f524242a299_Traceguids
0x140042681  mov     dl, r8b
0x140042684  lea     r9d, [r14+34h]
0x140042688  mov     [rsp+88h+var_68], rax
0x14004268d  mov     rcx, [rcx+40h]
0x140042691  call    WPP_RECORDER_SF_
0x140042696  mov     ebx, 0C000009Ah
0x14004269b  jmp     loc_140042804
0x1400426a0  shr     rdi, 1
0x1400426a3  jz      loc_1400427B3
0x1400426a9  mov     eax, ebx
0x1400426ab  mov     rdx, rdi
0x1400426ae  shr     rax, 1
0x1400426b1  mov     r8, r14
0x1400426b4  test    rax, rax
0x1400426b7  jz      short loc_1400426D6
0x1400426b9  movzx   ecx, word ptr [rsi]
0x1400426bc  test    cx, cx
0x1400426bf  jz      short loc_1400426D6
0x1400426c1  mov     [r8], cx
0x1400426c5  add     rsi, 2
0x1400426c9  add     r8, 2
0x1400426cd  dec     rax
0x1400426d0  sub     rdx, 1
0x1400426d4  jnz     short loc_1400426B4
0x1400426d6  mov     rax, rdx
0x1400426d9  lea     rcx, [r8-2]
0x1400426dd  neg     rax
0x1400426e0  mov     r9d, 80000005h
0x1400426e6  sbb     ebx, ebx
0x1400426e8  not     ebx
0x1400426ea  and     ebx, r9d
0x1400426ed  test    rdx, rdx
0x1400426f0  cmovnz  rcx, r8
0x1400426f4  mov     [rcx], r13w
0x1400426f8  jz      loc_1400427B8
0x1400426fe  mov     rcx, rdi
0x140042701  mov     rax, r14
0x140042704  cmp     [rax], r13w
0x140042708  jz      short loc_140042714
0x14004270a  add     rax, 2
0x14004270e  sub     rcx, 1
0x140042712  jnz     short loc_140042704
0x140042714  mov     rax, rcx
0x140042717  neg     rax
0x14004271a  sbb     ebx, ebx
0x14004271c  not     ebx
0x14004271e  and     ebx, 0C000000Dh
0x140042724  test    rcx, rcx
0x140042727  jz      short loc_140042731
0x140042729  mov     rax, rdi
0x14004272c  sub     rax, rcx
0x14004272f  jmp     short loc_140042734
0x140042731  mov     rax, r13
0x140042734  test    rcx, rcx
0x140042737  jz      short loc_14004279B
0x140042739  movzx   ecx, [rsp+88h+GuidString.Length]
0x14004273e  lea     rdx, [r14+rax*2]
0x140042742  mov     r8, [rsp+88h+GuidString.Buffer]
0x140042747  shr     rcx, 1
0x14004274a  sub     rdi, rax
0x14004274d  jz      short loc_140042771
0x14004274f  test    rcx, rcx
0x140042752  jz      short loc_140042771
0x140042754  movzx   eax, word ptr [r8]
0x140042758  test    ax, ax
0x14004275b  jz      short loc_140042771
0x14004275d  mov     [rdx], ax
0x140042760  add     r8, 2
0x140042764  add     rdx, 2
0x140042768  dec     rcx
0x14004276b  sub     rdi, 1
0x14004276f  jnz     short loc_14004274F
0x140042771  test    rdi, rdi
0x140042774  lea     rcx, [rdx-2]
0x140042778  mov     rax, rdi
0x14004277b  cmovnz  rcx, rdx
0x14004277f  neg     rax
0x140042782  sbb     ebx, ebx
0x140042784  not     ebx
0x140042786  and     ebx, r9d
0x140042789  mov     [rcx], r13w
0x14004278d  test    rdi, rdi
0x140042790  jz      short loc_14004279B
0x140042792  mov     [r15], r14
0x140042795  mov     [r12], ebp
0x140042799  jmp     short loc_140042804
0x14004279b  lea     rax, WPP_RECORDER_INITIALIZED
0x1400427a2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400427a9  jz      short loc_1400427F3
0x1400427ab  mov     r9d, 36h ; '6'
0x1400427b1  jmp     short loc_1400427CE
0x1400427b3  mov     ebx, 0C000000Dh
0x1400427b8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400427bf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400427c6  jz      short loc_1400427F3
0x1400427c8  mov     r9d, 35h ; '5'
0x1400427ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400427d5  lea     rax, WPP_f53708f2277a3aabca584f524242a299_Traceguids
0x1400427dc  mov     r8d, 2
0x1400427e2  mov     [rsp+88h+var_68], rax
0x1400427e7  mov     dl, r8b
0x1400427ea  mov     rcx, [rcx+40h]
0x1400427ee  call    WPP_RECORDER_SF_
0x1400427f3  xor     edx, edx; Tag
0x1400427f5  mov     rcx, r14; P
0x1400427f8  call    cs:__imp_ExFreePoolWithTag
0x1400427ff  nop     dword ptr [rax+rax+00h]
0x140042804  cmp     [rsp+88h+GuidString.Buffer], r13
0x140042809  jz      short loc_14004281C
0x14004280b  lea     rcx, [rsp+88h+GuidString]; UnicodeString
0x140042810  call    cs:__imp_RtlFreeUnicodeString
0x140042817  nop     dword ptr [rax+rax+00h]
0x14004281c  mov     eax, ebx
0x14004281e  add     rsp, 48h
0x140042822  pop     r15
0x140042824  pop     r14
0x140042826  pop     r13
0x140042828  pop     r12
0x14004282a  pop     rdi
0x14004282b  pop     rsi
0x14004282c  pop     rbp
0x14004282d  pop     rbx
0x14004282e  retn
```
