# AddChildSiblings(_DeviceTreeData *,_DeviceTreeNode *,ulong,int,int)

- ea: `0x18000312c`
- end: `0x18000370d`
- name: `?AddChildSiblings@@YAJPEAU_DeviceTreeData@@PEAU_DeviceTreeNode@@KHH@Z`
- size: `1505`
- prototype: `__int64 __fastcall(struct _DeviceTreeData *, struct _DeviceTreeNode *, unsigned int, int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18000312c`
- `0x180006514`

## callees

- `0x18000312c`
- `0x1800037f0`
- `0x180005724`
- `0x180005c80`
- `0x180006004`
- `0x18000873a`
- `0x180008760`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180003618`
- `KERNEL32!LocalFree` at `0x180003666`
- `KERNEL32!LocalFree` at `0x180003618`
- `KERNEL32!LocalFree` at `0x180003666`
- `KERNEL32!LocalAlloc` at `0x1800031a3`
- `KERNEL32!LocalAlloc` at `0x1800032ed`
- `KERNEL32!LocalAlloc` at `0x1800033e1`
- `KERNEL32!LocalAlloc` at `0x18000352e`
- `KERNEL32!LocalAlloc` at `0x1800031a3`
- `KERNEL32!LocalAlloc` at `0x1800032ed`
- `KERNEL32!LocalAlloc` at `0x1800033e1`
- `KERNEL32!LocalAlloc` at `0x18000352e`
- `USER32!LoadStringW` at `0x1800032bf`
- `USER32!LoadStringW` at `0x1800033b3`
- `USER32!LoadStringW` at `0x1800032bf`
- `USER32!LoadStringW` at `0x1800033b3`
- `CFGMGR32!CM_Get_Device_ID_ExW` at `0x1800034eb`
- `CFGMGR32!CM_Get_Device_ID_ExW` at `0x1800034eb`
- `CFGMGR32!CM_Get_Sibling_Ex` at `0x1800036bc`
- `CFGMGR32!CM_Get_Sibling_Ex` at `0x1800036bc`
- `CFGMGR32!CM_Get_Child_Ex` at `0x180003686`
- `CFGMGR32!CM_Get_Child_Ex` at `0x180003686`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x180003226`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x180003286`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x18000337a`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x18000346a`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x180003226`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x180003286`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x18000337a`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x18000346a`
- `CFGMGR32!CM_Get_DevNode_Status_Ex` at `0x18000349a`
- `CFGMGR32!CM_Get_DevNode_Status_Ex` at `0x18000349a`
- `SETUPAPI!pSetupGuidFromString` at `0x180003241`
- `SETUPAPI!pSetupGuidFromString` at `0x180003241`

## pseudocode

```c
__int64 __fastcall AddChildSiblings(struct _DeviceTreeData *a1, struct _DeviceTreeNode *a2, DEVINST a3, int a4, int a5)
{
  char *v5; // r15
  struct _DeviceTreeNode *v7; // rdi
  char *v9; // rax
  char *v10; // rbx
  char **v11; // rax
  _WORD *v12; // rax
  unsigned __int64 v13; // rdx
  __int64 v14; // rcx
  WCHAR *v15; // r8
  _WORD *v16; // rcx
  _WORD *v17; // rax
  unsigned __int64 v18; // rdx
  __int64 v19; // rcx
  WCHAR *v20; // r8
  _WORD *v21; // rcx
  _DWORD *v22; // r14
  _DWORD *v23; // rsi
  _DWORD *v24; // rdi
  CONFIGRET Device_ID; // eax
  __int64 v26; // rax
  _WORD *v27; // rax
  unsigned __int64 v28; // rdx
  __int64 v29; // rcx
  WCHAR *v30; // r8
  _WORD *v31; // rcx
  unsigned int *v32; // rdi
  int v33; // esi
  unsigned __int16 *v34; // r14
  unsigned int *v35; // rdi
  int v36; // esi
  unsigned __int16 *v37; // r14
  ULONG pulLength; // [rsp+40h] [rbp-C0h] BYREF
  DEVINST dnDevInst; // [rsp+48h] [rbp-B8h] BYREF
  DEVNODE pdnDevInst; // [rsp+50h] [rbp-B0h] BYREF
  struct _DeviceTreeNode *v42; // [rsp+58h] [rbp-A8h]
  WCHAR Buffer[259]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v44; // [rsp+266h] [rbp+166h]
  WCHAR Source[264]; // [rsp+270h] [rbp+170h] BYREF

  v42 = a2;
  dnDevInst = a3;
  pulLength = 0;
  v5 = (char *)a2 + 16;
  pdnDevInst = 0;
  if ( !a2 )
    v5 = (char *)a1 + 56;
  v7 = a2;
  if ( !a2 )
  {
    *((_QWORD *)v5 + 1) = v5;
    *(_QWORD *)v5 = v5;
  }
  if ( a4 > *((_DWORD *)a1 + 8) )
    *((_DWORD *)a1 + 8) = a4;
  while ( 1 )
  {
    v9 = (char *)LocalAlloc(0x40u, 0xA8u);
    v10 = v9;
    if ( !v9 )
      return 8;
    memset_0(v9, 0, 0xA8u);
    v11 = (char **)*((_QWORD *)v5 + 1);
    if ( *v11 != v5 )
      __fastfail(3u);
    *((_QWORD *)v10 + 1) = v11;
    *(_QWORD *)v10 = v5;
    *v11 = v10;
    *((_QWORD *)v5 + 1) = v10;
    *((_QWORD *)v10 + 3) = v10 + 16;
    *((_QWORD *)v10 + 2) = v10 + 16;
    *((_QWORD *)v10 + 9) = v7;
    *((_DWORD *)v10 + 24) = dnDevInst;
    *((_DWORD *)v10 + 30) = a4;
    pulLength = 520;
    if ( !CM_Get_DevNode_Registry_Property_ExW(dnDevInst, 9u, 0, Buffer, &pulLength, 0, 0) )
    {
      v44 = 0;
      pSetupGuidFromString(Buffer, v10 + 100);
    }
    *((_QWORD *)v10 + 7) = DevNodeToDriveLetter(dnDevInst);
    Buffer[0] = 0;
    pulLength = 520;
    if ( CM_Get_DevNode_Registry_Property_ExW(dnDevInst, 0xDu, 0, Buffer, &pulLength, 0, 0) || !Buffer[0] )
    {
      *((_QWORD *)v10 + 5) = 0;
    }
    else if ( *((_QWORD *)v10 + 7) && LoadStringW(hHotPlug, 0x461u, Source, 260) )
    {
      *((_QWORD *)v10 + 5) = FormatString(Source, Buffer, *((_QWORD *)v10 + 7));
    }
    else
    {
      v12 = LocalAlloc(0x40u, pulLength);
      *((_QWORD *)v10 + 5) = v12;
      if ( v12 )
      {
        v13 = (unsigned __int64)pulLength >> 1;
        if ( v13 )
        {
          v14 = 2147483646;
          v15 = Buffer;
          do
          {
            if ( !v14 )
              break;
            if ( !*v15 )
              break;
            *v12++ = *v15++;
            --v14;
            --v13;
          }
          while ( v13 );
          v16 = v12 - 1;
          if ( v13 )
            v16 = v12;
          *v16 = 0;
        }
      }
    }
    Buffer[0] = 0;
    pulLength = 520;
    if ( CM_Get_DevNode_Registry_Property_ExW(dnDevInst, 1u, 0, Buffer, &pulLength, 0, 0) || !Buffer[0] )
    {
      *((_QWORD *)v10 + 6) = 0;
    }
    else if ( *((_QWORD *)v10 + 7) && LoadStringW(hHotPlug, 0x461u, Source, 260) )
    {
      *((_QWORD *)v10 + 6) = FormatString(Source, Buffer, *((_QWORD *)v10 + 7));
    }
    else
    {
      v17 = LocalAlloc(0x40u, pulLength);
      *((_QWORD *)v10 + 6) = v17;
      if ( v17 )
      {
        v18 = (unsigned __int64)pulLength >> 1;
        if ( v18 )
        {
          v19 = 2147483646;
          v20 = Buffer;
          do
          {
            if ( !v19 )
              break;
            if ( !*v20 )
              break;
            *v17++ = *v20++;
            --v19;
            --v18;
          }
          while ( v18 );
          v21 = v17 - 1;
          if ( v18 )
            v21 = v17;
          *v21 = 0;
        }
      }
    }
    pulLength = 4;
    v22 = v10 + 116;
    if ( CM_Get_DevNode_Registry_Property_ExW(dnDevInst, 0x10u, 0, v10 + 116, &pulLength, 0, 0) )
      *v22 = 0;
    v23 = v10 + 156;
    v24 = v10 + 160;
    if ( CM_Get_DevNode_Status_Ex((PULONG)v10 + 40, (PULONG)v10 + 39, dnDevInst, 0, 0) )
    {
      *v24 = 0;
      *v23 = 0;
    }
    if ( (*v24 & 0x408) == 0 && (*(_BYTE *)v22 & 0x40) != 0 )
      *v23 = 10;
    *((_QWORD *)v10 + 8) = BuildLocationInformation(dnDevInst);
    Buffer[0] = 0;
    Device_ID = CM_Get_Device_ID_ExW(dnDevInst, Buffer, 0x104u, 0, 0);
    v44 = 0;
    if ( Device_ID || !Buffer[0] )
    {
      *((_QWORD *)v10 + 4) = 0;
      if ( Device_ID )
        goto LABEL_63;
    }
    else
    {
      v26 = -1;
      do
        ++v26;
      while ( Buffer[v26] );
      pulLength = 2 * v26 + 2;
      v27 = LocalAlloc(0x40u, pulLength);
      *((_QWORD *)v10 + 4) = v27;
      if ( v27 )
      {
        v28 = (unsigned __int64)pulLength >> 1;
        if ( v28 )
        {
          v29 = 2147483646;
          v30 = Buffer;
          do
          {
            if ( !v29 )
              break;
            if ( !*v30 )
              break;
            *v27++ = *v30++;
            --v29;
            --v28;
          }
          while ( v28 );
          v31 = v27 - 1;
          if ( v28 )
            v31 = v27;
          *v31 = 0;
        }
      }
    }
    *((_QWORD *)v10 + 16) = BuildDeviceRelationsList(Buffer, 4u, (unsigned __int16 *)v10 + 68);
    *((_QWORD *)v10 + 18) = BuildDeviceRelationsList(Buffer, 8u, (unsigned __int16 *)v10 + 76);
LABEL_63:
    if ( !a5 )
    {
      *((_DWORD *)v10 + 41) = 1;
      return 0;
    }
    v32 = (unsigned int *)*((_QWORD *)v10 + 16);
    v33 = *((unsigned __int16 *)v10 + 68);
    *((_DWORD *)v10 + 41) = 0;
    while ( v33 )
    {
      --v33;
      v34 = DevNodeToDriveLetter(*v32);
      if ( v34 )
      {
        AddChildSiblings(a1, (struct _DeviceTreeNode *)v10, *v32, a4 + 1, 0);
        LocalFree(v34);
      }
      ++v32;
    }
    v35 = (unsigned int *)*((_QWORD *)v10 + 18);
    v36 = *((unsigned __int16 *)v10 + 76);
    while ( v36 )
    {
      --v36;
      v37 = DevNodeToDriveLetter(*v35);
      if ( v37 )
      {
        AddChildSiblings(a1, (struct _DeviceTreeNode *)v10, *v35, a4 + 1, 0);
        LocalFree(v37);
      }
      ++v35;
    }
    if ( !CM_Get_Child_Ex(&pdnDevInst, dnDevInst, 0, 0) )
      AddChildSiblings(a1, (struct _DeviceTreeNode *)v10, pdnDevInst, a4 + 1, 1);
    if ( CM_Get_Sibling_Ex(&dnDevInst, dnDevInst, 0, 0) )
      return 0;
    v7 = v42;
  }
}

```

## disassembly

```asm
0x18000312c  push    rbp
0x18000312e  push    rbx
0x18000312f  push    rsi
0x180003130  push    rdi
0x180003131  push    r12
0x180003133  push    r13
0x180003135  push    r14
0x180003137  push    r15
0x180003139  lea     rbp, [rsp-398h]
0x180003141  sub     rsp, 498h
0x180003148  mov     rax, cs:__security_cookie
0x18000314f  xor     rax, rsp
0x180003152  mov     [rbp+3D0h+var_50], rax
0x180003159  xor     r14d, r14d
0x18000315c  mov     [rsp+4D0h+var_478], rdx
0x180003161  test    rdx, rdx
0x180003164  mov     [rsp+4D0h+dnDevInst], r8d
0x180003169  lea     rax, [rcx+38h]
0x18000316d  mov     [rsp+4D0h+var_490], r14d
0x180003172  lea     r15, [rdx+10h]
0x180003176  mov     [rsp+4D0h+pdnDevInst], r14d
0x18000317b  cmovz   r15, rax
0x18000317f  mov     r12d, r9d
0x180003182  mov     rdi, rdx
0x180003185  mov     r13, rcx
0x180003188  jnz     short loc_180003191
0x18000318a  mov     [r15+8], r15
0x18000318e  mov     [r15], r15
0x180003191  cmp     r12d, [rcx+20h]
0x180003195  jle     short loc_18000319B
0x180003197  mov     [rcx+20h], r12d
0x18000319b  mov     edx, 0A8h; uBytes
0x1800031a0  lea     ecx, [rdx-68h]; uFlags
0x1800031a3  call    cs:__imp_LocalAlloc
0x1800031a9  mov     rbx, rax
0x1800031ac  test    rax, rax
0x1800031af  jz      loc_1800036E5
0x1800031b5  xor     edx, edx; Val
0x1800031b7  mov     r8d, 0A8h; Size
0x1800031bd  mov     rcx, rax; void *
0x1800031c0  call    memset_0
0x1800031c5  mov     rax, [r15+8]
0x1800031c9  cmp     [rax], r15
0x1800031cc  jnz     loc_1800036DE
0x1800031d2  mov     [rbx+8], rax
0x1800031d6  lea     r9, [rsp+4D0h+Buffer]; Buffer
0x1800031db  mov     [rbx], r15
0x1800031de  xor     r8d, r8d; pulRegDataType
0x1800031e1  mov     [rax], rbx
0x1800031e4  lea     rax, [rbx+10h]
0x1800031e8  mov     [r15+8], rbx
0x1800031ec  mov     [rbx+18h], rax
0x1800031f0  mov     [rax], rax
0x1800031f3  lea     edx, [r8+9]; ulProperty
0x1800031f7  mov     [rbx+48h], rdi
0x1800031fb  mov     eax, [rsp+4D0h+dnDevInst]
0x1800031ff  mov     [rbx+60h], eax
0x180003202  lea     rax, [rsp+4D0h+var_490]
0x180003207  mov     [rbx+78h], r12d
0x18000320b  mov     ecx, [rsp+4D0h+dnDevInst]; dnDevInst
0x18000320f  mov     [rsp+4D0h+hMachine], r14; hMachine
0x180003214  mov     [rsp+4D0h+ulFlags], r14d; ulFlags
0x180003219  mov     [rsp+4D0h+pulLength], rax; pulLength
0x18000321e  mov     [rsp+4D0h+var_490], 208h
0x180003226  call    cs:__imp_CM_Get_DevNode_Registry_Property_ExW
0x18000322c  test    eax, eax
0x18000322e  jnz     short loc_180003247
0x180003230  lea     rdx, [rbx+64h]
0x180003234  mov     [rbp+3D0h+var_26A], r14w
0x18000323c  lea     rcx, [rsp+4D0h+Buffer]
0x180003241  call    cs:__imp_pSetupGuidFromString
0x180003247  mov     ecx, [rsp+4D0h+dnDevInst]; unsigned int
0x18000324b  call    ?DevNodeToDriveLetter@@YAPEAGK@Z; DevNodeToDriveLetter(ulong)
0x180003250  mov     [rbx+38h], rax
0x180003254  lea     r9, [rsp+4D0h+Buffer]; Buffer
0x180003259  mov     ecx, [rsp+4D0h+dnDevInst]; dnDevInst
0x18000325d  lea     rax, [rsp+4D0h+var_490]
0x180003262  xor     r8d, r8d; pulRegDataType
0x180003265  mov     [rsp+4D0h+hMachine], r14; hMachine
0x18000326a  mov     [rsp+4D0h+ulFlags], r14d; ulFlags
0x18000326f  mov     [rsp+4D0h+Buffer], r14w
0x180003275  mov     [rsp+4D0h+var_490], 208h
0x18000327d  lea     edx, [r8+0Dh]; ulProperty
0x180003281  mov     [rsp+4D0h+pulLength], rax; pulLength
0x180003286  call    cs:__imp_CM_Get_DevNode_Registry_Property_ExW
0x18000328c  test    eax, eax
0x18000328e  jnz     loc_180003344
0x180003294  cmp     [rsp+4D0h+Buffer], r14w
0x18000329a  jz      loc_180003344
0x1800032a0  cmp     [rbx+38h], r14
0x1800032a4  jz      short loc_1800032E4
0x1800032a6  mov     rcx, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; hInstance
0x1800032ad  lea     r8, [rbp+3D0h+Source]; lpBuffer
0x1800032b4  mov     r9d, 104h; cchBufferMax
0x1800032ba  mov     edx, 461h; uID
0x1800032bf  call    cs:__imp_LoadStringW
0x1800032c5  test    eax, eax
0x1800032c7  jz      short loc_1800032E4
0x1800032c9  mov     r8, [rbx+38h]
0x1800032cd  lea     rdx, [rsp+4D0h+Buffer]
0x1800032d2  lea     rcx, [rbp+3D0h+Source]; lpSource
0x1800032d9  call    ?FormatString@@YAPEAGPEBGZZ; FormatString(ushort const *,...)
0x1800032de  mov     [rbx+28h], rax
0x1800032e2  jmp     short loc_180003348
0x1800032e4  mov     edx, [rsp+4D0h+var_490]; uBytes
0x1800032e8  mov     ecx, 40h ; '@'; uFlags
0x1800032ed  call    cs:__imp_LocalAlloc
0x1800032f3  mov     [rbx+28h], rax
0x1800032f7  test    rax, rax
0x1800032fa  jz      short loc_180003348
0x1800032fc  mov     edx, [rsp+4D0h+var_490]
0x180003300  shr     rdx, 1
0x180003303  jz      short loc_180003348
0x180003305  mov     ecx, 7FFFFFFEh
0x18000330a  lea     r8, [rsp+4D0h+Buffer]
0x18000330f  test    rcx, rcx
0x180003312  jz      short loc_180003333
0x180003314  movzx   r9d, word ptr [r8]
0x180003318  test    r9w, r9w
0x18000331c  jz      short loc_180003333
0x18000331e  mov     [rax], r9w
0x180003322  add     r8, 2
0x180003326  add     rax, 2
0x18000332a  dec     rcx
0x18000332d  sub     rdx, 1
0x180003331  jnz     short loc_18000330F
0x180003333  test    rdx, rdx
0x180003336  lea     rcx, [rax-2]
0x18000333a  cmovnz  rcx, rax
0x18000333e  mov     [rcx], r14w
0x180003342  jmp     short loc_180003348
0x180003344  mov     [rbx+28h], r14
0x180003348  mov     ecx, [rsp+4D0h+dnDevInst]; dnDevInst
0x18000334c  lea     rax, [rsp+4D0h+var_490]
0x180003351  xor     r8d, r8d; pulRegDataType
0x180003354  mov     [rsp+4D0h+hMachine], r14; hMachine
0x180003359  mov     [rsp+4D0h+ulFlags], r14d; ulFlags
0x18000335e  lea     r9, [rsp+4D0h+Buffer]; Buffer
0x180003363  mov     [rsp+4D0h+Buffer], r14w
0x180003369  mov     [rsp+4D0h+var_490], 208h
0x180003371  lea     edx, [r8+1]; ulProperty
0x180003375  mov     [rsp+4D0h+pulLength], rax; pulLength
0x18000337a  call    cs:__imp_CM_Get_DevNode_Registry_Property_ExW
0x180003380  test    eax, eax
0x180003382  jnz     loc_180003438
0x180003388  cmp     [rsp+4D0h+Buffer], r14w
0x18000338e  jz      loc_180003438
0x180003394  cmp     [rbx+38h], r14
0x180003398  jz      short loc_1800033D8
0x18000339a  mov     rcx, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; hInstance
0x1800033a1  lea     r8, [rbp+3D0h+Source]; lpBuffer
0x1800033a8  mov     r9d, 104h; cchBufferMax
0x1800033ae  mov     edx, 461h; uID
0x1800033b3  call    cs:__imp_LoadStringW
0x1800033b9  test    eax, eax
0x1800033bb  jz      short loc_1800033D8
0x1800033bd  mov     r8, [rbx+38h]
0x1800033c1  lea     rdx, [rsp+4D0h+Buffer]
0x1800033c6  lea     rcx, [rbp+3D0h+Source]; lpSource
0x1800033cd  call    ?FormatString@@YAPEAGPEBGZZ; FormatString(ushort const *,...)
0x1800033d2  mov     [rbx+30h], rax
0x1800033d6  jmp     short loc_18000343C
0x1800033d8  mov     edx, [rsp+4D0h+var_490]; uBytes
0x1800033dc  mov     ecx, 40h ; '@'; uFlags
0x1800033e1  call    cs:__imp_LocalAlloc
0x1800033e7  mov     [rbx+30h], rax
0x1800033eb  test    rax, rax
0x1800033ee  jz      short loc_18000343C
0x1800033f0  mov     edx, [rsp+4D0h+var_490]
0x1800033f4  shr     rdx, 1
0x1800033f7  jz      short loc_18000343C
0x1800033f9  mov     ecx, 7FFFFFFEh
0x1800033fe  lea     r8, [rsp+4D0h+Buffer]
0x180003403  test    rcx, rcx
0x180003406  jz      short loc_180003427
0x180003408  movzx   r9d, word ptr [r8]
0x18000340c  test    r9w, r9w
0x180003410  jz      short loc_180003427
0x180003412  mov     [rax], r9w
0x180003416  add     r8, 2
0x18000341a  add     rax, 2
0x18000341e  dec     rcx
0x180003421  sub     rdx, 1
0x180003425  jnz     short loc_180003403
0x180003427  test    rdx, rdx
0x18000342a  lea     rcx, [rax-2]
0x18000342e  cmovnz  rcx, rax
0x180003432  mov     [rcx], r14w
0x180003436  jmp     short loc_18000343C
0x180003438  mov     [rbx+30h], r14
0x18000343c  mov     ecx, [rsp+4D0h+dnDevInst]; dnDevInst
0x180003440  lea     rax, [rsp+4D0h+var_490]
0x180003445  xor     edi, edi
0x180003447  mov     [rsp+4D0h+var_490], 4
0x18000344f  mov     [rsp+4D0h+hMachine], rdi; hMachine
0x180003454  lea     r14, [rbx+74h]
0x180003458  mov     [rsp+4D0h+ulFlags], edi; ulFlags
0x18000345c  mov     r9, r14; Buffer
0x18000345f  xor     r8d, r8d; pulRegDataType
0x180003462  mov     [rsp+4D0h+pulLength], rax; pulLength
0x180003467  lea     edx, [rdi+10h]; ulProperty
0x18000346a  call    cs:__imp_CM_Get_DevNode_Registry_Property_ExW
0x180003470  test    eax, eax
0x180003472  jz      short loc_180003477
0x180003474  mov     [r14], edi
0x180003477  mov     r8d, [rsp+4D0h+dnDevInst]; dnDevInst
0x18000347c  lea     rsi, [rbx+9Ch]
0x180003483  xor     eax, eax
0x180003485  lea     rdi, [rbx+0A0h]
0x18000348c  mov     rdx, rsi; pulProblemNumber
0x18000348f  mov     [rsp+4D0h+pulLength], rax; hMachine
0x180003494  mov     rcx, rdi; pulStatus
0x180003497  xor     r9d, r9d; ulFlags
0x18000349a  call    cs:__imp_CM_Get_DevNode_Status_Ex
0x1800034a0  xor     ecx, ecx
0x1800034a2  test    eax, eax
0x1800034a4  jz      short loc_1800034AA
0x1800034a6  mov     [rdi], ecx
0x1800034a8  mov     [rsi], ecx
0x1800034aa  test    dword ptr [rdi], 408h
0x1800034b0  jnz     short loc_1800034BE
0x1800034b2  test    byte ptr [r14], 40h
0x1800034b6  jz      short loc_1800034BE
0x1800034b8  mov     dword ptr [rsi], 0Ah
0x1800034be  mov     ecx, [rsp+4D0h+dnDevInst]; dnDevInst
0x1800034c2  call    ?BuildLocationInformation@@YAPEAGK@Z; BuildLocationInformation(ulong)
0x1800034c7  mov     [rbx+40h], rax
0x1800034cb  lea     rdx, [rsp+4D0h+Buffer]; Buffer
0x1800034d0  mov     ecx, [rsp+4D0h+dnDevInst]; dnDevInst
0x1800034d4  xor     r14d, r14d
0x1800034d7  xor     r9d, r9d; ulFlags
0x1800034da  mov     [rsp+4D0h+Buffer], r14w
0x1800034e0  mov     r8d, 104h; BufferLen
0x1800034e6  mov     [rsp+4D0h+pulLength], r14; hMachine
0x1800034eb  call    cs:__imp_CM_Get_Device_ID_ExW
0x1800034f1  mov     [rbp+3D0h+var_26A], r14w
0x1800034f9  test    eax, eax
0x1800034fb  jnz     loc_180003585
0x180003501  cmp     [rsp+4D0h+Buffer], r14w
0x180003507  jz      short loc_180003585
0x180003509  lea     rcx, [rsp+4D0h+Buffer]
0x18000350e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003512  inc     rax
0x180003515  cmp     [rcx+rax*2], r14w
0x18000351a  jnz     short loc_180003512
0x18000351c  lea     eax, ds:2[rax*2]
0x180003523  mov     ecx, 40h ; '@'; uFlags
0x180003528  mov     edx, eax; uBytes
0x18000352a  mov     [rsp+4D0h+var_490], eax
0x18000352e  call    cs:__imp_LocalAlloc
0x180003534  mov     [rbx+20h], rax
0x180003538  test    rax, rax
0x18000353b  jz      short loc_18000358D
0x18000353d  mov     edx, [rsp+4D0h+var_490]
0x180003541  shr     rdx, 1
0x180003544  jz      short loc_18000358D
0x180003546  mov     ecx, 7FFFFFFEh
0x18000354b  lea     r8, [rsp+4D0h+Buffer]
0x180003550  test    rcx, rcx
0x180003553  jz      short loc_180003574
0x180003555  movzx   r9d, word ptr [r8]
0x180003559  test    r9w, r9w
0x18000355d  jz      short loc_180003574
0x18000355f  mov     [rax], r9w
0x180003563  add     r8, 2
0x180003567  add     rax, 2
0x18000356b  dec     rcx
0x18000356e  sub     rdx, 1
0x180003572  jnz     short loc_180003550
0x180003574  test    rdx, rdx
0x180003577  lea     rcx, [rax-2]
0x18000357b  cmovnz  rcx, rax
0x18000357f  mov     [rcx], r14w
0x180003583  jmp     short loc_18000358D
0x180003585  mov     [rbx+20h], r14
0x180003589  test    eax, eax
0x18000358b  jnz     short loc_1800035C7
0x18000358d  lea     r8, [rbx+88h]; unsigned __int16 *
0x180003594  mov     edx, 4; ulFlags
0x180003599  lea     rcx, [rsp+4D0h+Buffer]; pszFilter
0x18000359e  call    ?BuildDeviceRelationsList@@YAPEAKPEAGK0@Z; BuildDeviceRelationsList(ushort *,ulong,ushort *)
0x1800035a3  lea     r8, [rbx+98h]; unsigned __int16 *
0x1800035aa  mov     [rbx+80h], rax
0x1800035b1  mov     edx, 8; ulFlags
0x1800035b6  lea     rcx, [rsp+4D0h+Buffer]; pszFilter
0x1800035bb  call    ?BuildDeviceRelationsList@@YAPEAKPEAGK0@Z; BuildDeviceRelationsList(ushort *,ulong,ushort *)
0x1800035c0  mov     [rbx+90h], rax
0x1800035c7  cmp     [rbp+3D0h+arg_20], r14d
0x1800035ce  jz      loc_1800036D0
0x1800035d4  mov     rdi, [rbx+80h]
0x1800035db  movzx   esi, word ptr [rbx+88h]
0x1800035e2  mov     [rbx+0A4h], r14d
0x1800035e9  jmp     short loc_180003625
0x1800035eb  mov     ecx, [rdi]; unsigned int
0x1800035ed  dec     esi
0x1800035ef  call    ?DevNodeToDriveLetter@@YAPEAGK@Z; DevNodeToDriveLetter(ulong)
0x1800035f4  mov     r14, rax
0x1800035f7  xor     eax, eax
0x1800035f9  test    r14, r14
0x1800035fc  jz      short loc_18000361E
  ... truncated ...
```
