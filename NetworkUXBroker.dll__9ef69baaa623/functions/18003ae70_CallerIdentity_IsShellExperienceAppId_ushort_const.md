# CallerIdentity::IsShellExperienceAppId(ushort const *)

- ea: `0x18003ae70`
- end: `0x18003af34`
- name: `?IsShellExperienceAppId@CallerIdentity@@YA_NPEBG@Z`
- size: `196`
- prototype: `bool __fastcall(LPCWCH lpString2, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180022194`

## callees

- `0x18003ae70`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003af10`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003af10`

## pseudocode

```c
char __fastcall CallerIdentity::IsShellExperienceAppId(LPCWCH lpString2, const unsigned __int16 *a2)
{
  char result; // al
  __int64 i; // rbx
  LPCWCH lpString1[11]; // [rsp+30h] [rbp-58h]

  lpString1[0] = L"Microsoft.Windows.ShellExperienceHost_cw5n1h2txyewy!App";
  lpString1[1] = L"Microsoft.Windows.StartMenuExperienceHost_cw5n1h2txyewy!App";
  lpString1[2] = L"Microsoft.Windows.StartMenuExperienceHost_cw5n1h2txyewy!FullTrustApp";
  lpString1[3] = L"5b04b775-356b-4aa0-aaf8-6491ffea5602_6f5w9sgpe6vgt!WP";
  lpString1[4] = L"StartAppVS_xbqbv2ksdy6ng!App";
  lpString1[5] = L"Microsoft.Windows.Cortana_cw5n1h2txyewy!ppleae38af2e007f4358a809ac99a64a67c1";
  lpString1[6] = L"Microsoft.Cortana_8wekyb3d8bbwe!ppleae38af2e007f4358a809ac99a64a67c1";
  lpString1[7] = L"MicrosoftWindows.Client.CBS_cw5n1h2txyewy!CortanaUIFullTrustApp";
  lpString1[8] = L"MicrosoftWindows.Search_cw5n1h2txyewy!CortanaUIFullTrustApp";
  lpString1[9] = L"HoloShell_cw5n1h2txyewy!HoloShell";
  result = 0;
  for ( i = 0; (unsigned int)i < 0xA; i = (unsigned int)(i + 1) )
  {
    if ( CompareStringOrdinal(lpString1[i], -1, lpString2, -1, 1) == 2 )
      return 1;
    result = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18003ae70  mov     r11, rsp
0x18003ae73  mov     [r11+8], rbx
0x18003ae77  push    rdi
0x18003ae78  sub     rsp, 80h
0x18003ae7f  lea     rax, aMicrosoftWindo; "Microsoft.Windows.ShellExperienceHost_c"...
0x18003ae86  mov     rdi, rcx
0x18003ae89  mov     [r11-58h], rax
0x18003ae8d  lea     rax, aMicrosoftWindo_0; "Microsoft.Windows.StartMenuExperienceHo"...
0x18003ae94  mov     [r11-50h], rax
0x18003ae98  lea     rax, aMicrosoftWindo_1; "Microsoft.Windows.StartMenuExperienceHo"...
0x18003ae9f  mov     [r11-48h], rax
0x18003aea3  lea     rax, a5b04b775356b4a; "5b04b775-356b-4aa0-aaf8-6491ffea5602_6f"...
0x18003aeaa  mov     [r11-40h], rax
0x18003aeae  lea     rax, aStartappvsXbqb; "StartAppVS_xbqbv2ksdy6ng!App"
0x18003aeb5  mov     [r11-38h], rax
0x18003aeb9  lea     rax, aMicrosoftWindo_2; "Microsoft.Windows.Cortana_cw5n1h2txyewy"...
0x18003aec0  mov     [r11-30h], rax
0x18003aec4  lea     rax, aMicrosoftCorta; "Microsoft.Cortana_8wekyb3d8bbwe!ppleae3"...
0x18003aecb  mov     [r11-28h], rax
0x18003aecf  lea     rax, aMicrosoftwindo; "MicrosoftWindows.Client.CBS_cw5n1h2txye"...
0x18003aed6  mov     [r11-20h], rax
0x18003aeda  lea     rax, aMicrosoftwindo_0; "MicrosoftWindows.Search_cw5n1h2txyewy!C"...
0x18003aee1  mov     [r11-18h], rax
0x18003aee5  lea     rax, aHoloshellCw5n1; "HoloShell_cw5n1h2txyewy!HoloShell"
0x18003aeec  mov     [r11-10h], rax
0x18003aef0  xor     al, al
0x18003aef2  xor     ebx, ebx
0x18003aef4  cmp     ebx, 0Ah
0x18003aef7  jnb     short loc_18003AF23
0x18003aef9  mov     rcx, [rsp+rbx*8+88h+lpString1]; lpString1
0x18003aefe  or      r9d, 0FFFFFFFFh; cchCount2
0x18003af02  or      edx, r9d; cchCount1
0x18003af05  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x18003af0d  mov     r8, rdi; lpString2
0x18003af10  call    cs:__imp_CompareStringOrdinal
0x18003af16  cmp     eax, 2
0x18003af19  jz      short loc_18003AF21
0x18003af1b  xor     al, al
0x18003af1d  inc     ebx
0x18003af1f  jmp     short loc_18003AEF4
0x18003af21  mov     al, 1
0x18003af23  mov     rbx, [rsp+88h+arg_0]
0x18003af2b  add     rsp, 80h
0x18003af32  pop     rdi
0x18003af33  retn
```
