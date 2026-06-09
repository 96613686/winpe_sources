# _tip_ModelInstallationCompletedTipTest::evaluate(void)

- ea: `0x18001e334`
- end: `0x18001e410`
- name: `?evaluate@_tip_ModelInstallationCompletedTipTest@@QEAAXXZ`
- size: `220`
- prototype: `void __fastcall(_tip_ModelInstallationCompletedTipTest *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001e290`

## callees

- `0x18001e334`

## string_xrefs

- `0x18001e340`: `reason::model_installation_failed`
- `0x18001e390`: `reason::model_installation_threw`

## pseudocode

```c
void __fastcall _tip_ModelInstallationCompletedTipTest::evaluate(_tip_ModelInstallationCompletedTipTest *this)
{
  const char *v1; // rdx
  char v2; // al
  const char *v3; // r8
  __int64 v4; // rax
  const char *v5; // rdx
  char v6; // al
  __int64 v7; // rax

  if ( *((_DWORD *)this + 4) == 1 )
  {
    v1 = "reason::model_installation_failed";
    v2 = 114;
    v3 = "reason::model_installation_failed";
    do
    {
      ++v1;
      if ( v2 == 58 )
        v3 = v1;
      v2 = *v1;
    }
    while ( *v1 );
    v4 = *((_QWORD *)this + 1);
    if ( !*(_BYTE *)(v4 + 152) )
    {
      *(_WORD *)(v4 + 154) = 1;
LABEL_8:
      *(_BYTE *)(v4 + 152) = 3;
      *(_QWORD *)(v4 + 160) = v3;
    }
  }
  else if ( *((_DWORD *)this + 4) == 2 )
  {
    v5 = "reason::model_installation_threw";
    v6 = 114;
    v3 = "reason::model_installation_threw";
    do
    {
      ++v5;
      if ( v6 == 58 )
        v3 = v5;
      v6 = *v5;
    }
    while ( *v5 );
    v4 = *((_QWORD *)this + 1);
    if ( !*(_BYTE *)(v4 + 152) )
    {
      *(_WORD *)(v4 + 154) = 2;
      goto LABEL_8;
    }
  }
  else
  {
    v7 = *((_QWORD *)this + 1);
    if ( (*(_DWORD *)(v7 + 56) & 0x200) != 0 )
    {
      if ( *(_BYTE *)(v7 + 152) )
        return;
      *(_BYTE *)(v7 + 152) = 1;
      *(_WORD *)(v7 + 154) = 0x8000;
    }
    else
    {
      if ( *(_BYTE *)(v7 + 152) )
        return;
      *(_BYTE *)(v7 + 152) = 3;
      *(_WORD *)(v7 + 154) = 16385;
    }
    *(_QWORD *)(v7 + 160) = 0;
  }
}

```

## disassembly

```asm
0x18001e334  mov     r9d, 1
0x18001e33a  cmp     [rcx+10h], r9d
0x18001e33e  jnz     short loc_18001E384
0x18001e340  lea     rdx, aReasonModelIns_0; "reason::model_installation_failed"
0x18001e347  mov     al, 72h ; 'r'
0x18001e349  mov     r8, rdx
0x18001e34c  add     rdx, r9
0x18001e34f  cmp     al, 3Ah ; ':'
0x18001e351  jnz     short loc_18001E356
0x18001e353  mov     r8, rdx
0x18001e356  mov     al, [rdx]
0x18001e358  test    al, al
0x18001e35a  jnz     short loc_18001E34C
0x18001e35c  mov     rax, [rcx+8]
0x18001e360  cmp     byte ptr [rax+98h], 0
0x18001e367  jnz     locret_18001E40F
0x18001e36d  mov     [rax+9Ah], r9w
0x18001e375  mov     byte ptr [rax+98h], 3
0x18001e37c  mov     [rax+0A0h], r8
0x18001e383  retn
0x18001e384  mov     r10d, 2
0x18001e38a  cmp     [rcx+10h], r10d
0x18001e38e  jnz     short loc_18001E3C3
0x18001e390  lea     rdx, aReasonModelIns; "reason::model_installation_threw"
0x18001e397  mov     al, 72h ; 'r'
0x18001e399  mov     r8, rdx
0x18001e39c  add     rdx, r9
0x18001e39f  cmp     al, 3Ah ; ':'
0x18001e3a1  jnz     short loc_18001E3A6
0x18001e3a3  mov     r8, rdx
0x18001e3a6  mov     al, [rdx]
0x18001e3a8  test    al, al
0x18001e3aa  jnz     short loc_18001E39C
0x18001e3ac  mov     rax, [rcx+8]
0x18001e3b0  cmp     byte ptr [rax+98h], 0
0x18001e3b7  jnz     short locret_18001E40F
0x18001e3b9  mov     [rax+9Ah], r10w
0x18001e3c1  jmp     short loc_18001E375
0x18001e3c3  mov     rax, [rcx+8]
0x18001e3c7  test    dword ptr [rax+38h], 200h
0x18001e3ce  jnz     short loc_18001E3EB
0x18001e3d0  cmp     byte ptr [rax+98h], 0
0x18001e3d7  jnz     short locret_18001E40F
0x18001e3d9  mov     byte ptr [rax+98h], 3
0x18001e3e0  mov     word ptr [rax+9Ah], 4001h
0x18001e3e9  jmp     short loc_18001E404
0x18001e3eb  cmp     byte ptr [rax+98h], 0
0x18001e3f2  jnz     short locret_18001E40F
0x18001e3f4  mov     [rax+98h], r9b
0x18001e3fb  mov     word ptr [rax+9Ah], 8000h
0x18001e404  mov     qword ptr [rax+0A0h], 0
0x18001e40f  retn
```
