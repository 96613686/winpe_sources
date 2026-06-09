# DwInitSnapShotTable1

- ea: `0x180028800`
- end: `0x18002b90a`
- name: `DwInitSnapShotTable1`
- size: `12554`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800271d4`

## callees

- `0x180028800`
- `0x18002b910`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180028810`
- `KERNEL32!LocalAlloc` at `0x180028810`

## string_xrefs

- `0x1800296ea`: `*CyanInMagentaDye`
- `0x180029667`: `*MagentaInCyanDye`
- `0x1800291f5`: `*UseSpaceForXMove?`
- `0x18002a7a6`: `*UseBMPFontCompression?`
- `0x18002a81b`: `*UseMode5Compression?`
- `0x180029435`: `*XMoveUnit`
- `0x180028a3c`: `*ResourceDLL`
- `0x180029096`: `*BadCursorMoveInGrxMode`
- `0x180029849`: `*MagentaInYellowDye`
- `0x18002975f`: `*YellowInMagentaDye`
- `0x180029351`: `*XMoveThreshold`
- `0x18002910b`: `*YMoveAttributes`
- `0x180029404`: `*YMoveThreshold`
- `0x18002951c`: `*LineSpacingMoveUnit`
- `0x18002ad22`: `*PrintSchemaPrivateNamespaceURI`
- `0x180029db6`: `*MoveToX0BeforeSetColor?`
- `0x1800294a7`: `*YMoveUnit`
- `0x18002926a`: `*AbsXMovesRightOnly?`

## pseudocode

```c
__int64 __fastcall DwInitSnapShotTable1(__int64 a1)
{
  __int64 result; // rax

  result = (__int64)LocalAlloc(0, 0x1C20u);
  *(_QWORD *)(a1 + 176) = result;
  if ( result )
  {
    *(_QWORD *)result = "*GPDSpecVersion";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 16LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 20LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 12LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 8LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 24LL) = 9;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 28LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 32LL) = "*GPDFileVersion";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 48LL) = 16;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 52LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 44LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 40LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 56LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 60LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 64LL) = "*GPDFileName";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 80LL) = 20;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 84LL) = 32;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 76LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 72LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 88LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 92LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 96LL) = "*MasterUnits";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 112LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 116LL) = 16;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 108LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 104LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 120LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 124LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 128LL) = "*ModelName";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 144LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 148LL) = 24;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 140LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 136LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 152LL) = 9;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 156LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 160LL) = "*PrinterType";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 176LL) = 68;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 180LL) = 40;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 172LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 168LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 184LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 188LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 192LL) = "*ResourceDLL";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 208LL) = 80;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 212LL) = 56;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 204LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 200LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 216LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 220LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 224LL) = "*MaxCopies";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 240LL) = 88;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 244LL) = 64;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 236LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 232LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 248LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 252LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 256LL) = "*DefaultCopies";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 272LL) = 92;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 276LL) = 68;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 268LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 264LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 280LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 284LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 288LL) = "*FontCartSlots";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 304LL) = 96;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 308LL) = 72;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 300LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 296LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 312LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 316LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 320LL) = "*OEMCustomData";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 336LL) = 24;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 340LL) = 80;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 332LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 328LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 344LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 348LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 352LL) = "*OEMCustomData";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 368LL) = 24;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 372LL) = 88;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 364LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 360LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 376LL) = 4096;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 380LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 384LL) = "*RotateCoordinate?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 400LL) = 116;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 404LL) = 92;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 396LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 392LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 408LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 412LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 416LL) = "*RotateRaster?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 432LL) = 124;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 436LL) = 96;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 428LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 424LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 440LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 444LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 448LL) = "*TextCaps";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 464LL) = 128;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 468LL) = 100;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 460LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 456LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 472LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 476LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 480LL) = "*RotateFont?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 496LL) = 132;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 500LL) = 104;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 492LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 488LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 504LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 508LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 512LL) = "*MemoryUsage";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 528LL) = 136;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 532LL) = 108;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 524LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 520LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 536LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 540LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 544LL) = "*ReselectFont";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 560LL) = 140;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 564LL) = 112;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 556LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 552LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 568LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 572LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 576LL) = "*OEMPrintingCallbacks";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 592LL) = 172;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 596LL) = 116;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 588LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 584LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 600LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 604LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 608LL) = "*CursorXAfterCR";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 624LL) = 176;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 628LL) = 120;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 620LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 616LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 632LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 636LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 640LL) = "*BadCursorMoveInGrxMode";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 656LL) = 180;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 660LL) = 124;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 652LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 648LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 664LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 668LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 672LL) = "*YMoveAttributes";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 688LL) = 196;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 692LL) = 128;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 684LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 680LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 696LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 700LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 704LL) = "*MaxLineSpacing";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 720LL) = 200;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 724LL) = 132;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 716LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 712LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 728LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 732LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 736LL) = "*UseSpaceForXMove?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 752LL) = 204;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 756LL) = 140;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 748LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 744LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 760LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 764LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 768LL) = "*AbsXMovesRightOnly?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 784LL) = 208;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 788LL) = 144;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 780LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 776LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 792LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 796LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 800LL) = "*EjectPageWithFF?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 816LL) = 188;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 820LL) = 136;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 812LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 808LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 824LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 828LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 832LL) = "*XMoveThreshold";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 848LL) = 212;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 852LL) = 148;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 844LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 840LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 856LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 860LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 864LL) = "*YMoveThreshold";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 880LL) = 216;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 884LL) = 152;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 876LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 872LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 888LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 892LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 896LL) = "*XMoveUnit";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 912LL) = 220;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 916LL) = 156;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 908LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 904LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 920LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 924LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 928LL) = "*YMoveUnit";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 944LL) = 224;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 948LL) = 160;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 940LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 936LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 952LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 956LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 960LL) = "*LineSpacingMoveUnit";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 976LL) = 228;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 980LL) = 164;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 972LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 968LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 984LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 988LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 992LL) = "*ChangeColorModeOnPage?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1008LL) = 232;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1012LL) = 168;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1004LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1000LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1016LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1020LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1024LL) = "*MagentaInCyanDye";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1040LL) = 240;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1044LL) = 172;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1036LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1032LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1048LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1052LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1056LL) = "*YellowInCyanDye";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1072LL) = 244;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1076LL) = 176;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1068LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1064LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1080LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1084LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1088LL) = "*CyanInMagentaDye";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1104LL) = 248;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1108LL) = 180;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1100LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1096LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1112LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1116LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1120LL) = "*YellowInMagentaDye";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1136LL) = 252;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1140LL) = 184;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1132LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1128LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1144LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1148LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1152LL) = "*CyanInYellowDye";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1168LL) = 256;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1172LL) = 188;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1164LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1160LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1176LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1180LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1184LL) = "*MagentaInYellowDye";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1200LL) = 260;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1204LL) = 192;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1196LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1192LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1208LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1212LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1216LL) = "*MaxNumPalettes";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1232LL) = 276;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1236LL) = 200;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1228LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1224LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1240LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1244LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1248LL) = "*OutputDataFormat";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1264LL) = 108;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1268LL) = 212;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1260LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1256LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1272LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1276LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1280LL) = "*OptimizeLeftBound?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1296LL) = 288;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1300LL) = 216;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1292LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1288LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1304LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1308LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1312LL) = "*StripBlanks";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1328LL) = 292;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1332LL) = 220;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1324LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1320LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1336LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1340LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1344LL) = "*RasterSendAllData?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1360LL) = 304;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1364LL) = 224;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1356LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1352LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1368LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1372LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1376LL) = "*CursorXAfterSendBlockData";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1392LL) = 316;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1396LL) = 228;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1388LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1384LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1400LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1404LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1408LL) = "*CursorYAfterSendBlockData";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1424LL) = 320;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1428LL) = 232;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1420LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1416LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1432LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1436LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1440LL) = "*MirrorRasterByte?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1456LL) = 324;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1460LL) = 252;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1452LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1448LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1464LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1468LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1472LL) = "*MirrorRasterPage?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1488LL) = 328;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1492LL) = 256;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1484LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1480LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1496LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1500LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1504LL) = "*PreAnalysisOptions";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1520LL) = 332;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1524LL) = 260;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1516LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1512LL) = bIsOnVistaAndAbove() != 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1528LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1532LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1536LL) = "*UseExpColorSelectCmd?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1552LL) = 264;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1556LL) = 236;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1548LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1544LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1560LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1564LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1568LL) = "*MoveToX0BeforeSetColor?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1584LL) = 268;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1588LL) = 240;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1580LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1576LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1592LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1596LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1600LL) = "*EnableGDIColorMapping?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1616LL) = 272;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1620LL) = 196;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1612LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1608LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1624LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1628LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1632LL) = "*SendMultipleRows?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1648LL) = 308;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1652LL) = 244;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1644LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1640LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1656LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1660LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1664LL) = "*DeviceFonts";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1680LL) = 336;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1684LL) = 264;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1676LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1672LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1688LL) = 40960;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1692LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1696LL) = "*DefaultFont";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1712LL) = 340;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1716LL) = 268;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1708LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1704LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1720LL) = 0x2000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1724LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1728LL) = "*MaxFontUsePerPage";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1744LL) = 356;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1748LL) = 272;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1740LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1736LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1752LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1756LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1760LL) = "*DefaultCTT";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1776LL) = 352;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1780LL) = 276;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1772LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1768LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1784LL) = 0x20000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1788LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1792LL) = "*LookaheadRegion";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1808LL) = 192;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1812LL) = 280;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1804LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1800LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1816LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1820LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1824LL) = "*TextYOffset";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1840LL) = 360;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1844LL) = 284;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1836LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1832LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1848LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1852LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1856LL) = "*CharPosition";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1872LL) = 364;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1876LL) = 288;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1868LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1864LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1880LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1884LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1888LL) = "*TTFSEnabled?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1904LL) = 344;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1908LL) = 292;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1900LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1896LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1912LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1916LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1920LL) = "*MinFontID";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1936LL) = 372;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1940LL) = 296;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1932LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1928LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1944LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1948LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1952LL) = "*MaxFontID";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1968LL) = 376;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1972LL) = 300;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1964LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1960LL) = 0xFFFF;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1976LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1980LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 1984LL) = "*MaxNumDownFonts";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2000LL) = 380;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2004LL) = 304;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1996LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 1992LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2008LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2012LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2016LL) = "*DLSymbolSet";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2032LL) = 392;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2036LL) = 308;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2028LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2024LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2040LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2044LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2048LL) = "*MinGlyphID";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2064LL) = 384;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2068LL) = 312;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2060LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2056LL) = 32;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2072LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2076LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2080LL) = "*MaxGlyphID";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2096LL) = 388;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2100LL) = 316;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2092LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2088LL) = 255;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2104LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2108LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2112LL) = "*DiffFontsPerByteMode?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2128LL) = 368;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2132LL) = 324;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2124LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2120LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2136LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2140LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2144LL) = "*CursorXAfterRectFill";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2160LL) = 408;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2164LL) = 328;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2156LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2152LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2168LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2172LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2176LL) = "*CursorYAfterRectFill";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2192LL) = 412;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2196LL) = 332;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2188LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2184LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2200LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2204LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2208LL) = "*MinGrayFill";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2224LL) = 416;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2228LL) = 336;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2220LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2216LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2232LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2236LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2240LL) = "*MaxGrayFill";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2256LL) = 420;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2260LL) = 340;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2252LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2248LL) = 100;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2264LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2268LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2272LL) = "*UseBMPFontCompression?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2288LL) = 432;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2292LL) = 352;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2284LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2280LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2296LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2300LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2304LL) = "*UseMode5Compression?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2320LL) = 436;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2324LL) = 356;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2316LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2312LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2328LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2332LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2336LL) = "*UseImageForHatchBrush?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2352LL) = 444;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2356LL) = 360;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2348LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2344LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2360LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2364LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2368LL) = "*UseHPGLPolylineEncoding?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2384LL) = 440;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2388LL) = 348;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2380LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2376LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2392LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2396LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2400LL) = "*XPSLandscapeMode";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2416LL) = 448;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2420LL) = 364;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2412LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2408LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2424LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2428LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2444LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2464LL) = "*MaxMultipleRowBytes";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2480LL) = 312;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2484LL) = 248;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2476LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2472LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2488LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2492LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2496LL) = "*TextHalftoneThreshold";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2512LL) = 424;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2516LL) = 344;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2508LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2504LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2520LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2524LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2528LL) = "*FontFormat";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2544LL) = 400;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2548LL) = 320;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2540LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2536LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2552LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2556LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2572LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2592LL) = "*ResourceDLL";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2608LL) = 80;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2612LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2604LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2600LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2616LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2620LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2624LL) = "*BidiQueryFile";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2640LL) = 32;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2644LL) = 312;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2636LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2632LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2648LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2652LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2656LL) = "*rcPersonalityID";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2672LL) = 76;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2676LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2668LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2664LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2680LL) = 16400;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2684LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2688LL) = "*Personality";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2704LL) = 72;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2708LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2700LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2696LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2712LL) = 6;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2716LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2720LL) = "*PrintSchemaPrivateNamespaceURI";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2736LL) = 28;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2740LL) = 184;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2732LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2728LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2744LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2748LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2752LL) = "*MaxCopies";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2768LL) = 88;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2772LL) = 60;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2764LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2760LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2776LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2780LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2784LL) = "*DefaultCopies";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2800LL) = 92;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2804LL) = 64;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2796LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2792LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2808LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2812LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2816LL) = "*rcPrinterIconID";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2832LL) = 100;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2836LL) = 148;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2828LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2824LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2840LL) = 0x10000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2844LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2848LL) = "*FontCartSlots";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2864LL) = 96;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2868LL) = 152;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2860LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2856LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2872LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2876LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2880LL) = "*HelpFile";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2896LL) = 104;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2900LL) = 168;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2892LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2888LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2904LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2908LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2912LL) = "*MasterUnits";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2928LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2932LL) = 172;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2924LL) = 8;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2920LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2936LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2940LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2944LL) = "*PrintRate";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2960LL) = 144;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2964LL) = 120;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2956LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2952LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2968LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2972LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 2976LL) = "*PrintRateUnit";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2992LL) = 148;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2996LL) = 124;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2988LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 2984LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3000LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3004LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3008LL) = "*PrintRatePPM";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3024LL) = 152;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3028LL) = 128;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3020LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3016LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3032LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3036LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3040LL) = "*LETTER_SIZE_EXISTS?  synthesized";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3056LL) = 456;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3060LL) = 140;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3052LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3048LL) = 512;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3064LL) = 0x40000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3068LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3072LL) = "*A4_SIZE_EXISTS?  synthesized";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3088LL) = 460;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3092LL) = 140;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3084LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3080LL) = 1024;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3096LL) = 0x40000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3100LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3116LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3136LL) = "*OutputOrderReversed? (global)";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3152LL) = 156;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3156LL) = 140;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3148LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3144LL) = 256;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3160LL) = 0x40000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3164LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3168LL) = "*ReverseBandOrderForEvenPages?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3184LL) = 160;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3188LL) = 140;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3180LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3176LL) = 0x2000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3192LL) = 0x40000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3196LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3200LL) = "*ReverseBandOrder?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3216LL) = 164;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3220LL) = 140;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3212LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3208LL) = 0x4000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3224LL) = 0x40000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3228LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3232LL) = "*NoPunctuationCharSubstitute?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3248LL) = 168;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3252LL) = 140;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3244LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3240LL) = 0x8000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3256LL) = 0x40000;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3260LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3264LL) = "*DraftQualitySettings";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3280LL) = 52;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3284LL) = 188;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3276LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3272LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3288LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3292LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3296LL) = "*BetterQualitySettings";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3312LL) = 56;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3316LL) = 192;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3308LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3304LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3320LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3324LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3328LL) = "*BestQualitySettings";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3344LL) = 60;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3348LL) = 196;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3340LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3336LL) = -1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3352LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3356LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3360LL) = "*DefaultQuality";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3376LL) = 64;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3380LL) = 200;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3372LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3368LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3384LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3388LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3392LL) = "*ChangeColorModeOnDoc?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3408LL) = 236;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3412LL) = 180;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3404LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3400LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3416LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3420LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3424LL) = "PrintProcDuplexOptions";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3440LL) = 428;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3444LL) = 296;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3436LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3432LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3448LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3452LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3456LL) = "*IsXPSDriver?";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3472LL) = 464;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3476LL) = 300;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3468LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3464LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3480LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3484LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3488LL) = "*JobPasscodeMinLength";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3504LL) = 468;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3508LL) = 304;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3500LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3496LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3512LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3516LL) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 176) + 3520LL) = "*JobPasscodeMaxLength";
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3536LL) = 472;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3540LL) = 308;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3532LL) = 4;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3528LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3544LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 176) + 3548LL) = 0;
    return 111;
  }
  return result;
}

```

## disassembly

```asm
0x180028800  push    rbx
0x180028802  sub     rsp, 30h
0x180028806  mov     rbx, rcx
0x180028809  mov     edx, 1C20h; uBytes
0x18002880e  xor     ecx, ecx; uFlags
0x180028810  call    cs:__imp_LocalAlloc
0x180028816  mov     [rbx+0B0h], rax
0x18002881d  test    rax, rax
0x180028820  jz      loc_18002B904
0x180028826  mov     [rsp+38h+arg_0], rbp
0x18002882b  lea     rcx, aGpdspecversion; "*GPDSpecVersion"
0x180028832  mov     [rax], rcx
0x180028835  lea     rcx, aGpdfileversion; "*GPDFileVersion"
0x18002883c  mov     rax, [rbx+0B0h]
0x180028843  mov     [rsp+38h+arg_8], rsi
0x180028848  mov     [rsp+38h+arg_10], rdi
0x18002884d  mov     [rsp+38h+arg_18], r12
0x180028852  xor     r12d, r12d
0x180028855  mov     [rax+10h], r12d
0x180028859  mov     rax, [rbx+0B0h]
0x180028860  mov     [rsp+38h+var_10], r14
0x180028865  mov     [rsp+38h+var_18], r15
0x18002886a  lea     r15, aMasterunits_0; "*MasterUnits"
0x180028871  mov     [rax+14h], r12d
0x180028875  mov     rax, [rbx+0B0h]
0x18002887c  mov     dword ptr [rax+0Ch], 8
0x180028883  mov     rax, [rbx+0B0h]
0x18002888a  mov     [rax+8], r12d
0x18002888e  mov     rax, [rbx+0B0h]
0x180028895  mov     dword ptr [rax+18h], 9
0x18002889c  mov     rax, [rbx+0B0h]
0x1800288a3  mov     [rax+1Ch], r12d
0x1800288a7  mov     rax, [rbx+0B0h]
0x1800288ae  mov     [rax+20h], rcx
0x1800288b2  lea     rcx, aGpdfilename; "*GPDFileName"
0x1800288b9  mov     rax, [rbx+0B0h]
0x1800288c0  mov     dword ptr [rax+30h], 10h
0x1800288c7  mov     rax, [rbx+0B0h]
0x1800288ce  mov     dword ptr [rax+34h], 8
0x1800288d5  mov     rax, [rbx+0B0h]
0x1800288dc  mov     dword ptr [rax+2Ch], 8
0x1800288e3  mov     rax, [rbx+0B0h]
0x1800288ea  mov     [rax+28h], r12d
0x1800288ee  mov     rax, [rbx+0B0h]
0x1800288f5  mov     dword ptr [rax+38h], 8
0x1800288fc  mov     rax, [rbx+0B0h]
0x180028903  mov     [rax+3Ch], r12d
0x180028907  mov     rax, [rbx+0B0h]
0x18002890e  mov     [rax+40h], rcx
0x180028912  lea     rcx, aModelname; "*ModelName"
0x180028919  mov     rax, [rbx+0B0h]
0x180028920  mov     dword ptr [rax+50h], 14h
0x180028927  mov     rax, [rbx+0B0h]
0x18002892e  mov     dword ptr [rax+54h], 20h ; ' '
0x180028935  mov     rax, [rbx+0B0h]
0x18002893c  mov     dword ptr [rax+4Ch], 8
0x180028943  mov     rax, [rbx+0B0h]
0x18002894a  mov     [rax+48h], r12d
0x18002894e  mov     rax, [rbx+0B0h]
0x180028955  mov     dword ptr [rax+58h], 8
0x18002895c  mov     rax, [rbx+0B0h]
0x180028963  mov     [rax+5Ch], r12d
0x180028967  mov     rax, [rbx+0B0h]
0x18002896e  mov     [rax+60h], r15
0x180028972  mov     rax, [rbx+0B0h]
0x180028979  mov     dword ptr [rax+70h], 4
0x180028980  mov     rax, [rbx+0B0h]
0x180028987  mov     dword ptr [rax+74h], 10h
0x18002898e  mov     rax, [rbx+0B0h]
0x180028995  mov     dword ptr [rax+6Ch], 8
0x18002899c  mov     rax, [rbx+0B0h]
0x1800289a3  mov     [rax+68h], r12d
0x1800289a7  mov     rax, [rbx+0B0h]
0x1800289ae  mov     dword ptr [rax+78h], 1
0x1800289b5  mov     rax, [rbx+0B0h]
0x1800289bc  mov     [rax+7Ch], r12d
0x1800289c0  mov     rax, [rbx+0B0h]
0x1800289c7  mov     [rax+80h], rcx
0x1800289ce  mov     rax, [rbx+0B0h]
0x1800289d5  mov     dword ptr [rax+90h], 8
0x1800289df  mov     rax, [rbx+0B0h]
0x1800289e6  mov     dword ptr [rax+94h], 18h
0x1800289f0  mov     rax, [rbx+0B0h]
0x1800289f7  mov     dword ptr [rax+8Ch], 8
0x180028a01  mov     rax, [rbx+0B0h]
0x180028a08  mov     [rax+88h], r12d
0x180028a0f  mov     rax, [rbx+0B0h]
0x180028a16  mov     dword ptr [rax+98h], 9
0x180028a20  mov     rax, [rbx+0B0h]
0x180028a27  mov     [rax+9Ch], r12d
0x180028a2e  mov     rax, [rbx+0B0h]
0x180028a35  lea     rcx, aPrintertype; "*PrinterType"
0x180028a3c  lea     rdi, aResourcedll_0; "*ResourceDLL"
0x180028a43  lea     rbp, aMaxcopies; "*MaxCopies"
0x180028a4a  lea     rsi, aDefaultcopies; "*DefaultCopies"
0x180028a51  mov     [rax+0A0h], rcx
0x180028a58  lea     r14, aFontcartslots; "*FontCartSlots"
0x180028a5f  mov     rax, [rbx+0B0h]
0x180028a66  lea     rcx, aOemcustomdata; "*OEMCustomData"
0x180028a6d  mov     dword ptr [rax+0B0h], 44h ; 'D'
0x180028a77  mov     rax, [rbx+0B0h]
0x180028a7e  mov     dword ptr [rax+0B4h], 28h ; '('
0x180028a88  mov     rax, [rbx+0B0h]
0x180028a8f  mov     dword ptr [rax+0ACh], 4
0x180028a99  mov     rax, [rbx+0B0h]
0x180028aa0  mov     [rax+0A8h], r12d
0x180028aa7  mov     rax, [rbx+0B0h]
0x180028aae  mov     dword ptr [rax+0B8h], 1
0x180028ab8  mov     rax, [rbx+0B0h]
0x180028abf  mov     [rax+0BCh], r12d
0x180028ac6  mov     rax, [rbx+0B0h]
0x180028acd  mov     [rax+0C0h], rdi
0x180028ad4  mov     rax, [rbx+0B0h]
0x180028adb  mov     dword ptr [rax+0D0h], 50h ; 'P'
0x180028ae5  mov     rax, [rbx+0B0h]
0x180028aec  mov     dword ptr [rax+0D4h], 38h ; '8'
0x180028af6  mov     rax, [rbx+0B0h]
0x180028afd  mov     dword ptr [rax+0CCh], 8
0x180028b07  mov     rax, [rbx+0B0h]
0x180028b0e  mov     [rax+0C8h], r12d
0x180028b15  mov     rax, [rbx+0B0h]
0x180028b1c  mov     dword ptr [rax+0D8h], 8
0x180028b26  mov     rax, [rbx+0B0h]
0x180028b2d  mov     [rax+0DCh], r12d
0x180028b34  mov     rax, [rbx+0B0h]
0x180028b3b  mov     [rax+0E0h], rbp
0x180028b42  mov     rax, [rbx+0B0h]
0x180028b49  mov     dword ptr [rax+0F0h], 58h ; 'X'
0x180028b53  mov     rax, [rbx+0B0h]
0x180028b5a  mov     dword ptr [rax+0F4h], 40h ; '@'
0x180028b64  mov     rax, [rbx+0B0h]
0x180028b6b  mov     dword ptr [rax+0ECh], 4
0x180028b75  mov     rax, [rbx+0B0h]
0x180028b7c  mov     dword ptr [rax+0E8h], 1
0x180028b86  mov     rax, [rbx+0B0h]
0x180028b8d  mov     [rax+0F8h], r12d
0x180028b94  mov     rax, [rbx+0B0h]
0x180028b9b  mov     [rax+0FCh], r12d
0x180028ba2  mov     rax, [rbx+0B0h]
0x180028ba9  mov     [rax+100h], rsi
0x180028bb0  mov     rax, [rbx+0B0h]
0x180028bb7  mov     dword ptr [rax+110h], 5Ch ; '\'
0x180028bc1  mov     rax, [rbx+0B0h]
0x180028bc8  mov     dword ptr [rax+114h], 44h ; 'D'
0x180028bd2  mov     rax, [rbx+0B0h]
0x180028bd9  mov     dword ptr [rax+10Ch], 4
0x180028be3  mov     rax, [rbx+0B0h]
0x180028bea  mov     dword ptr [rax+108h], 1
0x180028bf4  mov     rax, [rbx+0B0h]
0x180028bfb  mov     [rax+118h], r12d
0x180028c02  mov     rax, [rbx+0B0h]
0x180028c09  mov     [rax+11Ch], r12d
0x180028c10  mov     rax, [rbx+0B0h]
0x180028c17  mov     [rax+120h], r14
0x180028c1e  mov     rax, [rbx+0B0h]
0x180028c25  mov     dword ptr [rax+130h], 60h ; '`'
0x180028c2f  mov     rax, [rbx+0B0h]
0x180028c36  mov     dword ptr [rax+134h], 48h ; 'H'
0x180028c40  mov     rax, [rbx+0B0h]
0x180028c47  mov     dword ptr [rax+12Ch], 4
0x180028c51  mov     rax, [rbx+0B0h]
0x180028c58  mov     [rax+128h], r12d
0x180028c5f  mov     rax, [rbx+0B0h]
0x180028c66  mov     [rax+138h], r12d
0x180028c6d  mov     rax, [rbx+0B0h]
0x180028c74  mov     [rax+13Ch], r12d
0x180028c7b  mov     rax, [rbx+0B0h]
0x180028c82  mov     [rax+140h], rcx
0x180028c89  mov     rax, [rbx+0B0h]
0x180028c90  mov     dword ptr [rax+150h], 18h
0x180028c9a  mov     rax, [rbx+0B0h]
0x180028ca1  mov     dword ptr [rax+154h], 50h ; 'P'
0x180028cab  mov     rax, [rbx+0B0h]
0x180028cb2  mov     dword ptr [rax+14Ch], 8
0x180028cbc  mov     rax, [rbx+0B0h]
0x180028cc3  mov     [rax+148h], r12d
0x180028cca  mov     rax, [rbx+0B0h]
0x180028cd1  mov     dword ptr [rax+158h], 8
0x180028cdb  mov     rax, [rbx+0B0h]
0x180028ce2  mov     [rax+15Ch], r12d
0x180028ce9  mov     rax, [rbx+0B0h]
0x180028cf0  mov     [rax+160h], rcx
0x180028cf7  lea     rcx, aRotatecoordina; "*RotateCoordinate?"
0x180028cfe  mov     rax, [rbx+0B0h]
0x180028d05  mov     dword ptr [rax+170h], 18h
0x180028d0f  mov     rax, [rbx+0B0h]
0x180028d16  mov     dword ptr [rax+174h], 58h ; 'X'
0x180028d20  mov     rax, [rbx+0B0h]
0x180028d27  mov     dword ptr [rax+16Ch], 4
0x180028d31  mov     rax, [rbx+0B0h]
0x180028d38  mov     [rax+168h], r12d
0x180028d3f  mov     rax, [rbx+0B0h]
0x180028d46  mov     dword ptr [rax+178h], 1000h
0x180028d50  mov     rax, [rbx+0B0h]
0x180028d57  mov     [rax+17Ch], r12d
0x180028d5e  mov     rax, [rbx+0B0h]
0x180028d65  mov     [rax+180h], rcx
0x180028d6c  lea     rcx, aRotateraster; "*RotateRaster?"
0x180028d73  mov     rax, [rbx+0B0h]
0x180028d7a  mov     dword ptr [rax+190h], 74h ; 't'
0x180028d84  mov     rax, [rbx+0B0h]
0x180028d8b  mov     dword ptr [rax+194h], 5Ch ; '\'
0x180028d95  mov     rax, [rbx+0B0h]
0x180028d9c  mov     dword ptr [rax+18Ch], 4
0x180028da6  mov     rax, [rbx+0B0h]
0x180028dad  mov     [rax+188h], r12d
0x180028db4  mov     rax, [rbx+0B0h]
0x180028dbb  mov     [rax+198h], r12d
0x180028dc2  mov     rax, [rbx+0B0h]
0x180028dc9  mov     [rax+19Ch], r12d
0x180028dd0  mov     rax, [rbx+0B0h]
0x180028dd7  mov     [rax+1A0h], rcx
0x180028dde  lea     rcx, aTextcaps_0; "*TextCaps"
0x180028de5  mov     rax, [rbx+0B0h]
0x180028dec  mov     dword ptr [rax+1B0h], 7Ch ; '|'
0x180028df6  mov     rax, [rbx+0B0h]
0x180028dfd  mov     dword ptr [rax+1B4h], 60h ; '`'
0x180028e07  mov     rax, [rbx+0B0h]
0x180028e0e  mov     dword ptr [rax+1ACh], 4
0x180028e18  mov     rax, [rbx+0B0h]
0x180028e1f  mov     [rax+1A8h], r12d
0x180028e26  mov     rax, [rbx+0B0h]
0x180028e2d  mov     [rax+1B8h], r12d
0x180028e34  mov     rax, [rbx+0B0h]
0x180028e3b  mov     [rax+1BCh], r12d
0x180028e42  mov     rax, [rbx+0B0h]
0x180028e49  mov     [rax+1C0h], rcx
0x180028e50  lea     rcx, aRotatefont; "*RotateFont?"
0x180028e57  mov     rax, [rbx+0B0h]
0x180028e5e  mov     dword ptr [rax+1D0h], 80h
0x180028e68  mov     rax, [rbx+0B0h]
0x180028e6f  mov     dword ptr [rax+1D4h], 64h ; 'd'
0x180028e79  mov     rax, [rbx+0B0h]
0x180028e80  mov     dword ptr [rax+1CCh], 4
0x180028e8a  mov     rax, [rbx+0B0h]
0x180028e91  mov     dword ptr [rax+1C8h], 0FFFFFFFFh
0x180028e9b  mov     rax, [rbx+0B0h]
0x180028ea2  mov     [rax+1D8h], r12d
0x180028ea9  mov     rax, [rbx+0B0h]
0x180028eb0  mov     [rax+1DCh], r12d
0x180028eb7  mov     rax, [rbx+0B0h]
0x180028ebe  mov     [rax+1E0h], rcx
0x180028ec5  mov     rax, [rbx+0B0h]
0x180028ecc  mov     dword ptr [rax+1F0h], 84h
0x180028ed6  mov     rax, [rbx+0B0h]
0x180028edd  mov     dword ptr [rax+1F4h], 68h ; 'h'
0x180028ee7  mov     rax, [rbx+0B0h]
0x180028eee  mov     dword ptr [rax+1ECh], 4
0x180028ef8  mov     rax, [rbx+0B0h]
0x180028eff  mov     [rax+1E8h], r12d
0x180028f06  mov     rax, [rbx+0B0h]
0x180028f0d  mov     [rax+1F8h], r12d
0x180028f14  mov     rax, [rbx+0B0h]
0x180028f1b  lea     rcx, aMemoryusage; "*MemoryUsage"
0x180028f22  mov     [rax+1FCh], r12d
0x180028f29  mov     rax, [rbx+0B0h]
0x180028f30  mov     [rax+200h], rcx
0x180028f37  lea     rcx, aReselectfont; "*ReselectFont"
0x180028f3e  mov     rax, [rbx+0B0h]
0x180028f45  mov     dword ptr [rax+210h], 88h
0x180028f4f  mov     rax, [rbx+0B0h]
0x180028f56  mov     dword ptr [rax+214h], 6Ch ; 'l'
0x180028f60  mov     rax, [rbx+0B0h]
0x180028f67  mov     dword ptr [rax+20Ch], 4
0x180028f71  mov     rax, [rbx+0B0h]
0x180028f78  mov     dword ptr [rax+208h], 0FFFFFFFFh
0x180028f82  mov     rax, [rbx+0B0h]
0x180028f89  mov     [rax+218h], r12d
0x180028f90  mov     rax, [rbx+0B0h]
0x180028f97  mov     [rax+21Ch], r12d
0x180028f9e  mov     rax, [rbx+0B0h]
0x180028fa5  mov     [rax+220h], rcx
0x180028fac  lea     rcx, aOemprintingcal; "*OEMPrintingCallbacks"
0x180028fb3  mov     rax, [rbx+0B0h]
0x180028fba  mov     dword ptr [rax+230h], 8Ch
0x180028fc4  mov     rax, [rbx+0B0h]
0x180028fcb  mov     dword ptr [rax+234h], 70h ; 'p'
0x180028fd5  mov     rax, [rbx+0B0h]
0x180028fdc  mov     dword ptr [rax+22Ch], 4
0x180028fe6  mov     rax, [rbx+0B0h]
0x180028fed  mov     dword ptr [rax+228h], 0FFFFFFFFh
0x180028ff7  mov     rax, [rbx+0B0h]
0x180028ffe  mov     [rax+238h], r12d
0x180029005  mov     rax, [rbx+0B0h]
0x18002900c  mov     [rax+23Ch], r12d
0x180029013  mov     rax, [rbx+0B0h]
0x18002901a  mov     [rax+240h], rcx
0x180029021  lea     rcx, aCursorxaftercr; "*CursorXAfterCR"
0x180029028  mov     rax, [rbx+0B0h]
0x18002902f  mov     dword ptr [rax+250h], 0ACh
0x180029039  mov     rax, [rbx+0B0h]
0x180029040  mov     dword ptr [rax+254h], 74h ; 't'
0x18002904a  mov     rax, [rbx+0B0h]
0x180029051  mov     dword ptr [rax+24Ch], 4
0x18002905b  mov     rax, [rbx+0B0h]
0x180029062  mov     dword ptr [rax+248h], 0FFFFFFFFh
0x18002906c  mov     rax, [rbx+0B0h]
0x180029073  mov     [rax+258h], r12d
0x18002907a  mov     rax, [rbx+0B0h]
0x180029081  mov     [rax+25Ch], r12d
  ... truncated ...
```
